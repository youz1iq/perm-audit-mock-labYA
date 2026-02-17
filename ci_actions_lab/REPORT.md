# CI report (GitHub Actions)

## 1) Что такое CI (своими словами)
CI (Continuous Integration) — это своего рода автоматический фильтр, который проверяет код на ошибки до того, как он попадет в основной проект. Каждый раз, когда я загружаю изменения или создаю запрос на слияние (PR), система сама запускает тесты. Если тесты не проходят, код не объединяется с главной веткой, что защищает проект от поломок. Это позволяет разработчикам быстрее находить баги и поддерживать стабильность приложения без ручных проверок каждого коммита.

## 2) Что проверяет ваш workflow
Мой сценарий .github/workflows/tests.yml выполняет следующие шаги:

Checkout: копирует код из репозитория на виртуальную машину GitHub.

Setup-Python: устанавливает нужную версию интерпретатора (Python 3.11).

Install pytest: устанавливает библиотеку для тестирования напрямую через pip.

Run tests: запускает команду python -m pytest -q, проверяя корректность работы функций.

## 3) Ссылка на PR
https://github.com/youz1iq/perm-audit-mock-labYA/pull/1

## 4) Что было красным и как вы починили
Изначально Actions выдавал ошибку "pytest command not found" я добавил шаг python -m pip install pytest в файл workflow и проверил что тесты запускаются через модуль python -m pytest, чтобы избежать проблем с путями поиска модулей.

## 5) Команды
Вставь вывод:
1)PS C:\Users\ЮцевичА\Documents\17.02.26YA\ci_actions_lab_starter> python -m pytest -q
..                                                                                                  [100%]
2 passed in 0.02s

2)PS C:\Users\ЮцевичА\Documents\17.02.26YA\ci_actions_lab_starter> git log --oneline --decorate --graph --all
  
* 609bbf3 (HEAD -> ci/actions, tag: v0.4, origin/ci/actions) ci: add github actions to run pytest
* cce9f1d (origin/main, main) initial: add code and tests

3)PS C:\Users\ЮцевичА\Documents\17.02.26YA\ci_actions_lab_starter> git tag
v0.4

## 6) AI usage
В данной работе я использовал ИИ только как шаблон для отчета в REPORT.md и работоспособности tests.yml 

