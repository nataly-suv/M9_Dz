_______________________________________________

Часть 1: ESLint
Установка ESLint:

Инициализируйте новый проект npm:npm init -y

Установите ESLint: npm install eslint --save-dev

Инициализируйте конфигурацию ESLint: npm init @eslint/config@latest Следуйте инструкциям для настройки ESLint.

Создание конфигурационного файла .eslintrc:

После инициализации создайте файл .eslintrc.json и добавьте базовую конфигурацию:{

  "env": {

    "browser": true,

    "es2021": true

  },

  "extends": "eslint:recommended",

  "parserOptions": {

    "ecmaVersion": 12,

    "sourceType": "module"

  },

  "rules": {

    "indent": ["error", 2],

    "quotes": ["error", "single"],

    "semi": ["error", "always"]

  }

}

Проверка кода с помощью ESLint:

Создайте файл index.js и добавьте в него код с намеренными ошибками стиля.

Запустите ESLint для проверки кода: npx eslint index.js

______________________________________________ 

Часть 2: Prettier
Установка Prettier:

Установите Prettier:npm install --save-dev prettier

Создание конфигурационного файла .prettierrc:

Создайте файл .prettierrc с базовой конфигурацией:{

  "singleQuote": true,

  "semi": true

}

Интеграция Prettier с ESLint:

Установите необходимые пакеты: npm install --save-dev eslint-config-prettier eslint-plugin-prettier

Обновите ваш .eslintrc для использования Prettier:{

  "extends": [

    "eslint:recommended",

    "plugin:prettier/recommended"

  ]

}

Форматирование кода с помощью Prettier:

Запустите Prettier для форматирования кода:npx prettier --write index.js

____________________________________________________________

Часть 3: Lighthouse
Установка Lighthouse:

Установите Lighthouse глобально:npm install -g lighthouse

Анализ производительности веб-страницы:

Запустите локальный сервер:npx http-server

Запустите Lighthouse для анализа локального сервера:lighthouse http://127.0.0.1:8080 --output html --output-path ./report.html

_________________________________________________

Часть 4: Sentry
Регистрация в Sentry:

Зарегистрируйтесь и создайте новый проект на Sentry.

Установка и настройка Sentry:

Установите Sentry для вашего проекта:npm install @sentry/browser @sentry/tracing

Настройте Sentry в вашем проекте. Добавьте следующий код JavaScript-файл:import * as Sentry from '@sentry/browser';

import { Integrations } from '@sentry/tracing';

Sentry.init({

  dsn: 'YOUR_SENTRY_DSN',

  integrations: [new Integrations.BrowserTracing()],

  tracesSampleRate: 1.0,

});

Отслеживание ошибок:

Создайте намеренную ошибку в вашем коде, чтобы проверить, что Sentry правильно отслеживает ошибки.