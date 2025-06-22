<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>موقع تعليم بايثون مع لوحة تحكم</title>
<style>
  body { background: #000; color: #0f0; font-family: 'Tahoma', sans-serif; margin:0; padding:0; }
  header { background: #300; padding: 15px; text-align: center; color: #f00; font-size: 24px; }
  main { max-width: 900px; margin: 20px auto; padding: 10px; }
  .lesson { border: 2px solid #0f0; padding: 10px; margin-bottom: 20px; border-radius: 8px; background: #111; }
  .lesson img, video { max-width: 100%; border-radius: 8px; }
  .dashboard { background: #111; padding: 15px; border-radius: 12px; box-shadow: 0 0 15px #0f0; margin-bottom: 30px; }
  label { display: block; margin: 8px 0 4px; }
  input[type=text], textarea { width: 100%; padding: 8px; border-radius: 6px; border: none; background: #222; color: #0f0; }
  button { background: #900; color: #fff; border: none; padding: 10px 20px; border-radius: 8px; cursor: pointer; margin-top: 10px; }
  button:hover { background: #c00; }
  .btn-delete { background: #400; }
  .btn-delete:hover { background: #a00; }
</style>
</head>
<body>

<header>موقع تعليم بايثون - لوحة تحكم</header>

<main>

<section class="dashboard">
  <h2>لوحة التحكم</h2>
  <form id="lessonForm">
    <label for="title">عنوان الدرس:</label>
    <input type="text" id="title" required />
    
    <label for="content">شرح الدرس:</label>
    <textarea id="content" rows="4" required></textarea>
    
    <label for="video">رابط الفيديو (يوتيوب أو رابط مباشر):</label>
    <input type="text" id="video" placeholder="https://..." />
    
    <label for="image">رابط الصورة (اختياري):</label>
    <input type="text" id="image" placeholder="https://..." />
    
    <button type="submit">إضافة درس جديد</button>
  </form>
</section>

<section id="lessonsContainer">
  <h2>الدروس الحالية</h2>
  <!-- الدروس تظهر هنا -->
</section>

</main>

<script>
// جلب الدروس من التخزين المحلي
function loadLessons() {
  const lessons = JSON.parse(localStorage.getItem('lessons') || '[]');
  const container = document.getElementById('lessonsContainer');
  container.innerHTML = '<h2>الدروس الحالية</h2>';
  
  lessons.forEach((lesson, index) => {
    const lessonDiv = document.createElement('div');
    lessonDiv.className = 'lesson';
    lessonDiv.innerHTML = `
      <h3>${lesson.title}</h3>
      <p>${lesson.content}</p>
      ${lesson.video ? `<video controls src="${lesson.video}"></video>` : ''}
      ${lesson.image ? `<img src="${lesson.image}" alt="صورة الدرس">` : ''}
      <button class="btn-delete" onclick="deleteLesson(${index})">حذف الدرس</button>
    `;
    container.appendChild(lessonDiv);
  });
}

// حفظ درس جديد
document.getElementById('lessonForm').addEventListener('submit', e => {
  e.preventDefault();
  const title = document.getElementById('title').value.trim();
  const content = document.getElementById('content').value.trim();
  const video = document.getElementById('video').value.trim();
  const image = document.getElementById('image').value.trim();
  
  if (!title || !content) {
    alert('الرجاء تعبئة العنوان والشرح');
    return;
  }
  
  const lessons = JSON.parse(localStorage.getItem('lessons') || '[]');
  lessons.push({ title, content, video, image });
  localStorage.setItem('lessons', JSON.stringify(lessons));
  
  // تنظيف النموذج
  e.target.reset();
  
  // إعادة تحميل الدروس
  loadLessons();
});

// حذف درس
function deleteLesson(index) {
  const lessons = JSON.parse(localStorage.getItem('lessons') || '[]');
  lessons.splice(index, 1);
  localStorage.setItem('lessons', JSON.stringify(lessons));
  loadLessons();
}

// تحميل الدروس عند فتح الصفحة
loadLessons();
</script>

</body>
</html>
