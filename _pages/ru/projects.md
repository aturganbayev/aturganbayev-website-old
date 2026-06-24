---
layout: archive
title: "Проекты"
description: "Проекты Азамата Турганбаева по робототехнике: тактильное исследование поверхности UR5, автоматизированная сборка, навигация TurtleBot3, реабилитационный экзоскелет плечевого сустава с 5 степенями свободы и его 3D-печатный миниатюрный прототип-предшественник."
permalink: /ru/projects/
author_profile: true
lang: ru
---

<style>h1.page__title { display: none; }</style>

<style>
.exo-gallery { position: relative; width: 100%; max-width: 405px; margin: 0 auto; }
.exo-track {
  display: flex; overflow-x: auto; aspect-ratio: 3 / 4;
  scroll-snap-type: x mandatory; border-radius: 6px;
  scrollbar-width: none; -ms-overflow-style: none; -webkit-overflow-scrolling: touch;
  background: rgba(127, 127, 127, 0.08);
}
.exo-track::-webkit-scrollbar { display: none; }
.exo-slide {
  flex: 0 0 100%; width: 100%; height: 100%; object-fit: cover;
  scroll-snap-align: center; display: block; cursor: zoom-in;
}
.exo-arrow {
  position: absolute; top: 50%; transform: translateY(-50%); z-index: 2;
  width: 38px; height: 38px; border: none; border-radius: 50%;
  background: rgba(0, 0, 0, 0.45); color: #fff; font-size: 18px; line-height: 1;
  display: flex; align-items: center; justify-content: center;
  cursor: pointer; opacity: 0.85; transition: opacity 0.2s;
}
.exo-arrow:hover { opacity: 1; }
.exo-prev { left: 8px; }
.exo-next { right: 8px; }
.exo-thumbs { display: flex; justify-content: center; flex-wrap: wrap; gap: 6px; margin-top: 8px; }
.exo-thumb {
  padding: 0; border: 2px solid transparent; border-radius: 4px;
  background: none; line-height: 0; overflow: hidden; cursor: pointer; opacity: 0.65;
  transition: opacity 0.2s, border-color 0.2s;
}
.exo-thumb img { width: 54px; height: 54px; object-fit: cover; display: block; }
.exo-thumb:hover { opacity: 1; }
.exo-thumb.active { border-color: var(--global-link-color, #2a7ae2); opacity: 1; }
.exo-lightbox {
  position: fixed; inset: 0; z-index: 9999; padding: 20px;
  display: flex; align-items: center; justify-content: center;
  background: rgba(0, 0, 0, 0.9); cursor: zoom-out;
}
.exo-lightbox[hidden] { display: none; }
.exo-lightbox-img { max-width: 95%; max-height: 95%; object-fit: contain; border-radius: 4px; }
.exo-lightbox-close {
  position: absolute; top: 12px; right: 22px; color: #fff;
  font-size: 40px; line-height: 1; cursor: pointer;
}
</style>

<h1 style="margin-top: 0; margin-bottom: 20px;">Проекты</h1>

<h2 id="tactile-ur5" style="margin-top: 0; margin-bottom: 4px;">
  Тактильное исследование поверхности с помощью UR5 &nbsp;<a href="https://github.com/aturganbayev/tactile_UR5" style="font-size: 0.8em; font-weight: normal;">GitHub</a>
</h2>
<p style="margin-top: 0; margin-bottom: 4px;">
  <em>Май 2026 – настоящее время</em> &nbsp;|&nbsp; <a href="https://tact.nu.edu.kz/">Лаборатория тактильной робототехники</a> &nbsp;|&nbsp; Астана, Казахстан
</p>
<p style="margin-top: 0; margin-bottom: 8px;">
  <strong>Инструменты и технологии:</strong> UR5, URScript, Python, trimesh, NumPy, SciPy (ICP), pandas, Matplotlib, Docker (URSim), силовой датчик ATI Nano17, NI-DAQ
</p>
<ul style="margin-top: 0; margin-bottom: 8px;">
  <li>Создал сквозной пайплайн для автоматического тактильного исследования силиконового конуса с помощью коллаборативного робота UR5, от геометрии поверхности из CAD-модели до выполнения последовательностей касаний с синхронной записью силы контакта как на симулированном, так и на реальном роботе.</li>
  <li>Сэмплировал 3000 точек поверхности с нормалями из STL-модели конуса с помощью <code>trimesh</code>, затем откалибровал относительно базового фрейма робота методом ICP с фиксированной вертикальной осью и подбором только смещения (без вращения, с осью конуса, зафиксированной вертикально, чтобы избежать ложного наклона из-за точек калибровки, сосредоточенных у вершины), достигнув точности совмещения около 2,2&nbsp;мм RMS.</li>
  <li>Сгенерировал схемы касаний для полного покрытия поверхности и для 15 вертикальных полос вокруг конуса с масштабируемым по высоте наклоном ориентации (5°–15°) для зазора инструмента, затем выполнил их через собственный решатель прямой/обратной кинематики UR5 на Python (необходимый, поскольку встроенный в контроллер решатель IK с одним начальным приближением не сходится для точек, разнесённых вокруг конуса), передавая URScript-последовательности «подход–нажатие–отвод» по сырому TCP-сокету.</li>
  <li>Синхронизировал показания силы ATI Nano17 с потоком TCP-поз UR5 в реальном времени через NI-DAQ, автоматически определяя каждое нажатие и записывая его пиковую силу и позу для последующего анализа.</li>
</ul>
<div style="margin-top: 10px;">
  <iframe width="720" height="405" src="https://www.youtube.com/embed/ED0S0Vk0w-s" title="Tactile Surface Exploration with UR5" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen style="max-width: 100%;"></iframe>
</div>

<hr style="margin: 30px 0;">

<h2 style="margin-top: 0; margin-bottom: 4px;">
  Автоматизированная сборка фонарика с помощью UR5 &nbsp;<a href="https://github.com/aturganbayev/ME5286_UR5_Flashlight_Assembly#me5286-lab-4--ur5-flashlight-assembly" style="font-size: 0.8em; font-weight: normal;">GitHub</a> &nbsp;<a href="/files/ME5286_Flashlight_Assembly.pdf" style="font-size: 0.8em; font-weight: normal;">Отчёт</a>
</h2>
<p style="margin-top: 0; margin-bottom: 4px;">
  <em>Март 2026</em> &nbsp;|&nbsp; ME 5286 – Робототехника, Университет Миннесоты &nbsp;|&nbsp; Миннеаполис, MN
</p>
<p style="margin-top: 0; margin-bottom: 8px;">
  <strong>Инструменты и технологии:</strong> UR5, RoboDK, Python, планирование движения в декартовом и суставном пространстве, пневматическое крепление
</p>
<ul style="margin-top: 0; margin-bottom: 8px;">
  <li>Запрограммировал коллаборативного робота UR5 через Python API RoboDK для автономной сборки трёхкомпонентного фонарика (корпус, батарея, торцевая крышка) без участия человека.</li>
  <li>Определил 15 декартовых целевых поз для операций захвата, перемещения и вставки компонентов; использовал движение в пространстве суставов для быстрых переходов и линейное декартово движение вблизи точек контакта для предотвращения столкновений.</li>
  <li>Реализовал многоходовую процедуру предварительного завинчивания с последующим финальным затягиванием с контролем момента, скоординированную с пневматическим патроном и оптическим датчиком для надёжной фиксации деталей.</li>
  <li>Вся последовательность сборки выполнена за 1 минуту 39 секунд, в рамках требования в 110 секунд.</li>
</ul>
<div style="margin-top: 10px;">
  <iframe width="720" height="405" src="https://www.youtube.com/embed/OAarKcr0SdI" title="UR5 Flashlight Assembly" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen style="max-width: 100%;"></iframe>
</div>

<hr style="margin: 30px 0;">

<h2 style="margin-top: 0; margin-bottom: 4px;">
  Обход препятствий и навигация по маркерам ArUco на TurtleBot3 &nbsp;<a href="https://github.com/aturganbayev/CSCI5551-EE5271_Turtlebot_Navigation" style="font-size: 0.8em; font-weight: normal;">GitHub</a> &nbsp;<a href="/files/CSCI5551_Final_Project.pdf" style="font-size: 0.8em; font-weight: normal;">Отчёт</a>
</h2>
<p style="margin-top: 0; margin-bottom: 4px;">
  <em>Осень 2025</em> &nbsp;|&nbsp; Финальный проект CSCI 5551 / EE 5271, Университет Миннесоты &nbsp;|&nbsp; Миннеаполис, MN
</p>
<p style="margin-top: 0; margin-bottom: 8px;">
  <strong>Инструменты и технологии:</strong> TurtleBot3 Burger, ROS2 Humble, LiDAR, камера Raspberry Pi, Gazebo, RViz, Python
</p>
<ul style="margin-top: 0; margin-bottom: 8px;">
  <li>Разработал систему обхода препятствий на основе LiDAR для TurtleBot3 Burger с использованием двух ROS2-узлов: <code>obstacle_detector</code> (контролирует передний сектор LiDAR и публикует булевы топики об обнаружении препятствий) и <code>obstacle_avoidance</code> (переопределяет команды скорости для поворота и отступления при обнаружении препятствия в пределах 30 см).</li>
  <li>Интегрировал камеру Raspberry Pi на TurtleBot3 Burger, откалибровал её внутренние параметры с помощью пакета ROS2 на основе шахматной доски и добавил статический TF-фрейм для корректного представления положения камеры относительно базового звена робота.</li>
  <li>Реализовал отслеживание и следование по маркерам ArUco: узел <code>aruco_follower</code> совмещает визуальное направление на маркер с данными дальности LiDAR для движения робота на заданное расстояние к цели, останавливаясь при выходе маркера из поля зрения камеры.</li>
  <li>Протестировал оба алгоритма сначала в симуляции Gazebo, затем перенёс на реального робота с настройкой фильтрации шума LiDAR для надёжной работы в реальных условиях.</li>
</ul>
<div style="margin-top: 10px;">
  <iframe width="720" height="405" src="https://www.youtube.com/embed/5Qi0RW_q2Dw" title="TurtleBot3 Obstacle Avoidance & ArUco Navigation" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen style="max-width: 100%;"></iframe>
</div>

<hr style="margin: 30px 0;">

<h2 id="exoskeleton" style="margin-top: 0; margin-bottom: 4px;">
  Реабилитационный экзоскелет плечевого сустава &nbsp;<a href="https://cemrr.nu.edu.kz/ru/news/9" style="font-size: 0.8em; font-weight: normal;">Новости</a> &nbsp;<a href="https://www.youtube.com/watch?v=BF6AlbPFsx4&t=535s" style="font-size: 0.8em; font-weight: normal;">Интервью</a>
</h2>
<p style="margin-top: 0; margin-bottom: 4px;">
  <em>Сентябрь 2023 – Апрель 2025</em> &nbsp;|&nbsp; Назарбаев Университет &amp; <a href="https://cemrr.nu.edu.kz/en">CEMRR</a> &nbsp;|&nbsp; Астана, Казахстан
</p>
<p style="margin-top: 0; margin-bottom: 8px;">
  <strong>Инструменты и технологии:</strong> САПР, 3D-печать, проектирование четырёхзвенных механизмов, кабельно-приводные параллельные механизмы, механическое прототипирование
</p>
<ul style="margin-top: 0; margin-bottom: 8px;">
  <li>Спроектировал и собрал 5-DOF гибридный роботизированный экзоскелет плечевого сустава, комбинацию 2-DOF вращательного четырёхзвенного механизма и 3-DOF кабельно-приводного параллельного механизма, обеспечивающий движения плеча в полном диапазоне с сохранением выравнивания с центром вращения плечелопаточного сустава.</li>
  <li>Разработал 3D-печатные миниатюрные модели прототипа для проверки сопряжения механизма с человеком перед масштабированием до полноразмерного устройства.</li>
  <li>Создал полностью собранный носимый экзоскелет для интенсивных задачно-специфичных упражнений пациентов после инсульта, объединив механическое проектирование с клиническими требованиями реабилитации.</li>
  <li>Работа началась как дипломный проект бакалавриата в Назарбаев Университете и была расширена до полнофункционального устройства в Центре передовых исследований в области медицинской робототехники (CEMRR).</li>
</ul>
<div class="exo-gallery" style="margin-top: 10px;">
  <div class="exo-track">
    <img class="exo-slide" src="/images/exoskeleton/1.jpg" alt="Реабилитационный экзоскелет плечевого сустава, фото 1 из 4" loading="lazy">
    <img class="exo-slide" src="/images/exoskeleton/2.jpg" alt="Реабилитационный экзоскелет плечевого сустава, фото 2 из 4" loading="lazy">
    <img class="exo-slide" src="/images/exoskeleton/3.jpg" alt="Реабилитационный экзоскелет плечевого сустава, фото 3 из 4" loading="lazy">
    <img class="exo-slide" src="/images/exoskeleton/4.jpg" alt="Реабилитационный экзоскелет плечевого сустава, фото 4 из 4" loading="lazy">
  </div>
  <button type="button" class="exo-arrow exo-prev" aria-label="Предыдущее фото">&#10094;</button>
  <button type="button" class="exo-arrow exo-next" aria-label="Следующее фото">&#10095;</button>
  <div class="exo-thumbs"></div>
  <div class="exo-lightbox" hidden>
    <span class="exo-lightbox-close" aria-hidden="true">&times;</span>
    <img class="exo-lightbox-img" src="" alt="">
  </div>
</div>

<hr style="margin: 30px 0;">

<h2 id="mini-shoulder" style="margin-top: 0; margin-bottom: 4px;">
  3D-печатная миниатюрная модель сопряжения плечевого механизма человека и робота &nbsp;<a href="https://ieeexplore.ieee.org/document/10458641" style="font-size: 0.8em; font-weight: normal;">Статья</a>
</h2>
<p style="margin-top: 0; margin-bottom: 4px;">
  <em>Январь 2023 – Сентябрь 2023</em> &nbsp;|&nbsp; Назарбаев Университет &nbsp;|&nbsp; Астана, Казахстан
</p>
<p style="margin-top: 0; margin-bottom: 8px;">
  <strong>Инструменты и технологии:</strong> SolidWorks, MATLAB, кинематика четырёхзвенных механизмов, кабельно-приводные параллельные механизмы, 3D-печать
</p>
<ul style="margin-top: 0; margin-bottom: 8px;">
  <li>Спроектировал 5-DOF миниатюрный механизм сопряжения плечевого сустава, объединяющий 2-DOF четырёхзвенный кривошипно-коромысловый механизм для плечевого пояса с 3-DOF кабельно-приводным параллельным механизмом для плечелопаточного сустава, моделируя три вращательные и две поступательные степени свободы плеча.</li>
  <li>Вывел прямую и обратную кинематику как для четырёхзвенного механизма, так и для кабельно-приводного механизма, затем проверил уравнения относительно CAD-модели в SolidWorks с помощью MATLAB, добившись совпадения длин кабелей и углов суставов с точностью до 1–2&nbsp;мм и нескольких градусов.</li>
  <li>Разработал механизм предварительного натяжения для устранения провисания и схода кабелей, а также собрал регулируемый 3D-печатный прототип с переставляемыми точками крепления кабелей для проверки различных стратегий сопряжения.</li>
  <li>Этот базовый прототип позже стал основой для полноразмерного 5-DOF экзоскелета, разработанного в CEMRR.</li>
</ul>
<div class="exo-gallery" style="margin-top: 10px;">
  <div class="exo-track">
    <img class="exo-slide" src="/images/mini_shoulder/prototype.jpg" alt="3D-печатный прототип миниатюрного механизма плеча, фото 1 из 3" loading="lazy">
    <img class="exo-slide" src="/images/mini_shoulder/cas.jpg" alt="Детализация суставов CAD-модели миниатюрного механизма плеча, фото 2 из 3" loading="lazy">
    <img class="exo-slide" src="/images/mini_shoulder/sketch.jpg" alt="Обзор CAD-модели миниатюрного механизма плеча, фото 3 из 3" loading="lazy">
  </div>
  <button type="button" class="exo-arrow exo-prev" aria-label="Предыдущее фото">&#10094;</button>
  <button type="button" class="exo-arrow exo-next" aria-label="Следующее фото">&#10095;</button>
  <div class="exo-thumbs"></div>
  <div class="exo-lightbox" hidden>
    <span class="exo-lightbox-close" aria-hidden="true">&times;</span>
    <img class="exo-lightbox-img" src="" alt="">
  </div>
</div>

<script>
(function () {
  function initGallery(gallery) {
    var track = gallery.querySelector('.exo-track');
    var slides = [].slice.call(track.querySelectorAll('.exo-slide'));
    var thumbsWrap = gallery.querySelector('.exo-thumbs');
    var lightbox = gallery.querySelector('.exo-lightbox');
    var lightboxImg = lightbox ? lightbox.querySelector('.exo-lightbox-img') : null;
    var current = 0;

    slides.forEach(function (img, i) {
      var b = document.createElement('button');
      b.type = 'button';
      b.className = 'exo-thumb' + (i === 0 ? ' active' : '');
      b.setAttribute('aria-label', 'Перейти к фото ' + (i + 1));
      var t = document.createElement('img');
      t.src = img.src; t.alt = '';
      b.appendChild(t);
      b.addEventListener('click', function () { goTo(i); });
      thumbsWrap.appendChild(b);
    });
    var thumbs = [].slice.call(thumbsWrap.children);

    function goTo(i) {
      i = Math.max(0, Math.min(slides.length - 1, i));
      track.scrollTo({ left: i * track.clientWidth, behavior: 'smooth' });
    }
    function setActive(i) {
      if (i === current) return;
      current = i;
      thumbs.forEach(function (d, j) { d.classList.toggle('active', j === i); });
    }

    var raf;
    track.addEventListener('scroll', function () {
      if (raf) cancelAnimationFrame(raf);
      raf = requestAnimationFrame(function () {
        setActive(Math.round(track.scrollLeft / track.clientWidth));
      });
    });
    gallery.querySelector('.exo-prev').addEventListener('click', function () { goTo((current - 1 + slides.length) % slides.length); });
    gallery.querySelector('.exo-next').addEventListener('click', function () { goTo((current + 1) % slides.length); });

    if (lightbox && lightboxImg) {
      slides.forEach(function (img) {
        img.addEventListener('click', function () {
          lightboxImg.src = img.src;
          lightboxImg.alt = img.alt;
          lightbox.hidden = false;
        });
      });
      lightbox.addEventListener('click', function () { lightbox.hidden = true; });
    }
  }
  function init() { [].slice.call(document.querySelectorAll('.exo-gallery')).forEach(initGallery); }
  if (document.readyState === 'loading') {
    document.addEventListener('DOMContentLoaded', init);
  } else {
    init();
  }
})();
</script>
