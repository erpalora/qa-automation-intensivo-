Tutorial basico de Git para proyectos QA Automation
Inicialización del repositorio

# Inicia el repositorio (solo la primera vez)
git init

# Conecta tu repo local con GitHub (cambia la URL por la tuya)
git remote add origin https://github.com/tu_usuario/qa-bizagi-intensivo.git

Crear y trabajar en ramas
# Crear una nueva rama para pytest
git checkout -b feature/pytest

# Agregar archivos nuevos
git add python/tests/test_login.py

# Confirmar los cambios
git commit -m "feat(pytest): agregar test de login básico"

Cambiar de rama cuando se vaya a trabajar con Selenium:

git checkout -b feature/selenium

Subir cambios a GitHub
# Subir la rama actual
git push origin feature/pytest

Simular un pull Requets (en GitHub)
Ve a tu repositorio en GitHub.

Haz clic en "Compare & pull request".

Agrega un mensaje:
feat(pytest): Agregar pruebas de login con fixtures y reportes

Asigna la revisión a otro colaborador (o a ti misma si estás sola).

Haz clic en "Merge pull request".

  GNU nano 5.9                    TUTORIAL_GIT.md                     Modified

git checkout -b feature/selenium

Subir cambios a GitHub
# Subir la rama actualgit push origin feature/pytest

Simular un pull Requets (en GitHub)
Ve a tu repositorio en GitHub.

Haz clic en "Compare & pull request".

Agrega un mensaje:
feat(pytest): Agregar pruebas de login con fixtures y reportes

Asigna la revisión a otro colaborador (o a ti misma si estás sola).

Haz clic en "Merge pull request".



^G Help      ^O Write Out ^W Where Is  ^K Cut       ^T Execute   ^C Location
^X Exit      ^R Read File ^\ Replace   ^U Paste     ^J Justify   ^/ Go To Line

Fusionar ramas localmente
# Cambia a la rama principal
git checkout main

# Fusiona la rama de trabajo
git merge feature/pytest

CI/CD Con GitHub Actions

Ejemplo de archivo .github/workflows/python-tests.yml:
name: Python Tests

on: [push, pull_request]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Setup Python
        uses: actions/setup-python@v2
        with:
          python-version: '3.10'
      - name: Install dependencies
        run: pip install -r requirements.txt
      - name: Run pytest
        run: pytest python/tests/ --html=python/reports/report.html

Comandos utiles:
qa-bizagi-intensivo/
├── python/
│   ├── tests/
│   └── reports/
├── dotnet/
├── jmeter/
├── certificados/
├── .github/workflows/
│   └── python-tests.yml
├── README.md
└── TUTORIAL_GIT.md

Buenas practicas:
✔️ Usa nombres claros para ramas: feature/, bugfix/, hotfix/
✔️ Commits cortos y descriptivos.
✔️ Mantén tu main siempre funcional.
✔️ Integra tus pruebas en GitHub Actions.
git add TUTORIAL_GIT.md
fatal: pathspec 'TUTORIAL_GIT.md' did not match any files
bash: t: command not found

