
name: Build GUHVIP FF APK

on:
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Baixar projeto
        uses: actions/checkout@v4

      - name: Configurar Java
        uses: actions/setup-java@v4
        with:
          distribution: temurin
          java-version: '17'

      - name: Configurar Gradle
        uses: gradle/actions/setup-gradle@v4

      - name: Compilar Optimizer
        working-directory: optimizer
        run: gradle assembleDebug

      - name: Guardar APK
        uses: actions/upload-artifact@v4
        with:
          name: GUHVIP-FF-Optimizer-APK
          path: optimizer/app/build/outputs/apk/debug/*.apk
