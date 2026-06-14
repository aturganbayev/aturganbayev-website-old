---
layout: archive
title: "Проекты"
permalink: /ru/projects/
author_profile: true
lang: ru
---

<style>h1.page__title { display: none; }</style>

<h1 style="margin-top: 0; margin-bottom: 20px;">Проекты</h1>

<h2 style="margin-top: 0; margin-bottom: 4px;">
  Автоматизированная сборка фонарика с помощью UR5 &nbsp;<a href="https://github.com/aturganbayev/ME5286_UR5_Flashlight_Assembly#me5286-lab-4--ur5-flashlight-assembly" style="font-size: 0.6em; font-weight: normal;">GitHub</a> &nbsp;<a href="/files/ME5286_Flashlight_Assembly.pdf" style="font-size: 0.6em; font-weight: normal;">Отчёт</a>
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
  <li>Вся последовательность сборки выполнена за 1 минуту 39 секунд — в рамках требования в 110 секунд.</li>
</ul>
<div style="margin-top: 10px;">
  <iframe width="720" height="405" src="https://www.youtube.com/embed/OAarKcr0SdI" title="UR5 Flashlight Assembly" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen style="max-width: 100%;"></iframe>
</div>

<hr style="margin: 30px 0;">

<h2 style="margin-top: 0; margin-bottom: 4px;">
  Обход препятствий и навигация по маркерам ArUco на TurtleBot3 &nbsp;<a href="https://github.com/aturganbayev/CSCI5551-EE5271_Turtlebot_Navigation" style="font-size: 0.6em; font-weight: normal;">GitHub</a> &nbsp;<a href="/files/CSCI5551_Final_Project.pdf" style="font-size: 0.6em; font-weight: normal;">Отчёт</a>
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

<h2 style="margin-top: 0; margin-bottom: 4px;">
  Реабилитационный экзоскелет плечевого сустава
</h2>
<p style="margin-top: 0; margin-bottom: 4px;">
  <em>Апрель 2022 – Апрель 2025</em> &nbsp;|&nbsp; Назарбаев Университет &amp; <a href="https://cemrr.nu.edu.kz/en">CEMRR</a> &nbsp;|&nbsp; Астана, Казахстан
</p>
<p style="margin-top: 0; margin-bottom: 8px;">
  <strong>Инструменты и технологии:</strong> САПР, 3D-печать, проектирование четырёхзвенных механизмов, кабельно-приводные параллельные механизмы, механическое прототипирование
</p>
<ul style="margin-top: 0; margin-bottom: 8px;">
  <li>Спроектировал и собрал 5-DOF гибридный роботизированный экзоскелет плечевого сустава — комбинацию 2-DOF вращательного четырёхзвенного механизма и 3-DOF кабельно-приводного параллельного механизма — обеспечивающий движения плеча в полном диапазоне с сохранением выравнивания с центром вращения плечелопаточного сустава.</li>
  <li>Разработал 3D-печатные миниатюрные модели прототипа для проверки сопряжения механизма с человеком перед масштабированием до полноразмерного устройства.</li>
  <li>Создал полностью собранный носимый экзоскелет для интенсивных задачно-специфичных упражнений пациентов после инсульта, объединив механическое проектирование с клиническими требованиями реабилитации.</li>
  <li>Работа началась как дипломный проект бакалавриата в Назарбаев Университете и была расширена до полнофункционального устройства в Центре передовых исследований в области медицинской робототехники (CEMRR).</li>
</ul>
