# 🚗 CarTracker — Android App

## Инсталация и стартиране

### 1. Отваряне в Android Studio
1. Отвори Android Studio
2. **File → Open** → избери папката `CarTracker`
3. Изчакай Gradle sync да приключи (~2-3 мин)

---

### 2. Google Maps API ключ (ЗАДЪЛЖИТЕЛНО)

Без API ключ картите **няма да работят**.

#### Как да получиш безплатен ключ:
1. Отвори https://console.cloud.google.com
2. Създай нов проект (или избери съществуващ)
3. Отиди в **APIs & Services → Library**
4. Активирай:
   - **Maps SDK for Android**
   - **Fused Location Provider API**
5. Отиди в **APIs & Services → Credentials**
6. Натисни **+ CREATE CREDENTIALS → API key**
7. Копирай ключа

#### Добавяне в проекта:
Отвори файла `secrets.properties` (в корена на проекта):
```
MAPS_API_KEY=AIzaSy...ТВОЯТ_КЛЮЧ_ТУК...
```

---

### 3. Стартиране на телефон/емулатор
1. Включи **USB Debugging** на телефона:
   - Settings → About Phone → натисни 7 пъти Build Number
   - Settings → Developer Options → USB Debugging ON
2. Свържи телефона с USB
3. В Android Studio натисни **Run ▶** (Shift+F10)

---

## Функционалности

| Функция | Описание |
|---|---|
| 🚗 **Коли** | Добавяне/редактиране на коли с резервоар, пробег, праг за гориво |
| 🗺 **Маршрути** | GPS проследяване + ръчно добавяне, история, Google Maps преглед |
| ⛽ **Зареждания** | История на зарежданията, автоматично изчисляване на цена |
| 📊 **Статистика** | Среден разход л/100км, пробег, разходи за гориво |
| 🔔 **Напомняния** | Ежедневни push notifications по зададен час |
| ⚠️ **Предупреждения** | Автоматично известие при ниско гориво (% или литри) |

## Архитектура
- **MVVM** с LiveData + ViewModel
- **Room** база данни (3 таблици: cars, routes, refuelings)
- **Hilt** за dependency injection
- **Navigation Component** + Safe Args
- **WorkManager** за периодични напомняния
- **FusedLocationProviderClient** за GPS

