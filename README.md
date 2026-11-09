# Umear Visuals 1.1.0 (Fabric 1.21.4)

Исходники восстановлены по вашему jar (структура Module / Setting / Modules сохранена, конфиг `config/umear_visuals.json` совместим) + всё из «Дня 2».

## Сборка
Локально: `gradle build` (JDK 21) → `build/libs/umear-visuals-1.1.0.jar`.
С телефона: залей папку в GitHub-репозиторий, вкладка Actions → build → скачай артефакт `umear-visuals-jar`.

## ВАЖНО
Код написан без компиляции (в моей среде нет JDK и библиотек Minecraft). Если сборка упадёт — пришли лог ошибки, поправлю.
Самые рискованные места (имена Yarn 1.21.4): `GameRenderer.renderBlur`, `BackgroundRenderer.applyFog`/`Fog`,
`HeldItemRenderer.renderFirstPersonItem` (MixinExtras `@WrapMethod`), `DrawContext.drawTexture(... color)`.
Миксины в `umear.mixins.json` помечены `required:false`, поэтому сбой одного не роняет игру.

## Что нового
Исправлено: watermark — непрозрачная подложка + текстура с явным ARGB (раньше PNG был почти весь полупрозрачным);
FPS/CPS/Reach/Combo — один модуль **Info HUD**; все цвета теперь всегда с альфой 255.

Visuals: View Model, Target ESP (Box/Outline/Circle/Ring/Halo; цвет Статичный/Радуга/Градиент), Fog Changer,
Aspect Ratio (слайдер + пресеты), Swing Animation (режимы + скорость + длительность), Particles (Ванильные / Свои: круг, звезда, сердце, снежинка).
Combat: Hit Color, Dynamic Crosshair (Плюс/Точка/Круг/X/Скобки), Info HUD.
Misc: Client Sounds, Custom Font (Default/Uniform/Runic), GUI Blur, GUI Animation (Fade/Scale/Slide/Bounce, открытие и закрытие),
HUD Editor (перетаскивание, колёсико = размер, привязка), Notifications (3 стиля), Custom Theme (6 пресетов + Custom).

Не сделано: Chams (заменён на Box с заливкой); собственный TTF-шрифт (нужен файл шрифта в ресурсах).
