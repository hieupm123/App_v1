This is a new [**React Native**](https://reactnative.dev) project, bootstrapped using [`@react-native-community/cli`](https://github.com/react-native-community/cli).

# Getting Started

> **Note**: Make sure you have completed the [Set Up Your Environment](https://reactnative.dev/docs/set-up-your-environment) guide before proceeding.

## Step 1: Start Metro

First, you will need to run **Metro**, the JavaScript build tool for React Native.

To start the Metro dev server, run the following command from the root of your React Native project:

```sh
# Using npm
npm start

# OR using Yarn
yarn start
```

## Step 2: Build and run your app

With Metro running, open a new terminal window/pane from the root of your React Native project, and use one of the following commands to build and run your Android or iOS app:

### Android

```sh
# Using npm
npm run android

# OR using Yarn
yarn android
```

### iOS

For iOS, remember to install CocoaPods dependencies (this only needs to be run on first clone or after updating native deps).

The first time you create a new project, run the Ruby bundler to install CocoaPods itself:

```sh
bundle install
```

Then, and every time you update your native dependencies, run:

```sh
bundle exec pod install
```

For more information, please visit [CocoaPods Getting Started guide](https://guides.cocoapods.org/using/getting-started.html).

```sh
# Using npm
npm run ios

# OR using Yarn
yarn ios
```

If everything is set up correctly, you should see your new app running in the Android Emulator, iOS Simulator, or your connected device.

This is one way to run your app — you can also build it directly from Android Studio or Xcode.

## Step 3: Modify your app

Now that you have successfully run the app, let's make changes!

Open `App.tsx` in your text editor of choice and make some changes. When you save, your app will automatically update and reflect these changes — this is powered by [Fast Refresh](https://reactnative.dev/docs/fast-refresh).

When you want to forcefully reload, for example to reset the state of your app, you can perform a full reload:

- **Android**: Press the <kbd>R</kbd> key twice or select **"Reload"** from the **Dev Menu**, accessed via <kbd>Ctrl</kbd> + <kbd>M</kbd> (Windows/Linux) or <kbd>Cmd ⌘</kbd> + <kbd>M</kbd> (macOS).
- **iOS**: Press <kbd>R</kbd> in iOS Simulator.


# Các folder chính

# README - Ứng dụng Chụp Ảnh React Native (AI Pose & Editor)

Ứng dụng React Native hỗ trợ chụp ảnh, gợi ý pose bằng AI và chỉnh sửa ảnh, theo cấu trúc MVC.

## Cấu trúc Thư mục Chính

*   **`/android` & `/ios`**: Mã nguồn gốc cho từng nền tảng.
*   **`/assets`**: Tài sản tĩnh (hình ảnh, font, **model AI trong `assets/models/`**).
*   **`/src`**: Mã nguồn chính của ứng dụng.
    *   **`/controllers` (C)**: Xử lý logic, điều phối giữa Model và View.
        *   `CameraController.js`, `PoseController.js`, `EditorController.js`
    *   **`/models` (M)**: Quản lý dữ liệu, trạng thái, logic AI.
        *   `AIModel.js` (tải/chạy AI), `ImageState.js`, `PoseData.js`
    *   **`/navigation`**: Thiết lập điều hướng màn hình (`AppNavigator.js`).
    *   **`/services`**: Các dịch vụ hỗ trợ (xử lý ảnh, API).
        *   `ImageProcessingService.js`, `AIService.js`
    *   **`/views` (V)**: Giao diện người dùng.
        *   `/screens`: Các màn hình ( `CameraScreen.js`, `EditorScreen.js`, `PoseSuggestionScreen.js`).
        *   `/components`: UI component tái sử dụng (`PoseOverlay.js`, `EditingToolbar.js`).
    *   `App.js`: Component gốc trong `src`, khởi tạo điều hướng.
*   **`index.js`**: Điểm vào chính của ứng dụng React Native.
*   **`package.json`**: Quản lý thư viện và scripts dự án.
*   **`app.json`**: Cấu hình chung của ứng dụng.

## Mô hình MVC

*   **View (Giao diện)**: Hiển thị dữ liệu, nhận tương tác người dùng.
*   **Controller (Điều khiển)**: Nhận input từ View, gọi Model xử lý, cập nhật lại View.
*   **Model (Dữ liệu & Logic)**: Lưu trữ trạng thái, xử lý nghiệp vụ (bao gồm tương tác với model AI).

## Chức năng chính (dự kiến)

1.  **Chụp ảnh**: Sử dụng camera thiết bị.
2.  **Gợi ý Pose (AI)**: Model AI phân tích khung hình, đề xuất các tư thế tạo dáng.
3.  **Chỉnh sửa ảnh**: Các công cụ cơ bản (filter, crop, rotate, etc.).

## Các tệp cấu hình quan trọng khác

*   `.eslintrc.js`, `.prettierrc.js`: Linting và formatting code.
*   `babel.config.js`: Cấu hình trình biên dịch JavaScript.
*   `metro.config.js`: Cấu hình Metro bundler.