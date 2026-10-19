name: Build APK
on: workflow_dispatch
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - run: unzip cafe_app.zip
      - uses: subosito/flutter-action@v2
        with:
          channel: stable
      - run: |
          cd cafe_app
          flutter create --platforms=android --project-name cafe_app .
          flutter pub get
          flutter build apk --release
      - uses: actions/upload-artifact@v4
        with:
          name: cafe-apk
          path: cafe_app/build/app/outputs/flutter-apk/app-release.apk
