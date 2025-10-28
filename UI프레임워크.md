# 큰 갈래

* **네이티브 Win32 계열**

  * **Win32 API**: C/C++ 저수준 API. 최저 레벨, 학습 곡선 큼.
  * **MFC**: C++ 클래스로 Win32를 감싼 전통 GUI 프레임워크. SDI/MDI, 대화상자 중심 앱에 적합.

* **.NET 데스크톱 계열**

  * **Windows Forms**: .NET의 고전 폼 기반 UI. 빠른 RAD, 단순한 레이아웃.
  * **WPF**: C#/XAML, 벡터·데이터바인딩·MVVM에 강함. 풍부한 데스크톱 UI 표준.

* **현대 XAML & Windows App SDK**

  * **WinUI 3**: 최신 Windows용 XAML UI 레이어. C#/C++ 지원, Win32 데스크톱(패키지/비패키지)에서 사용.
  * **Windows App SDK**: WinUI 3, App Lifecycle, 윈도우링, 알림 등 현대 Windows API 묶음.

* **UWP (유지 관리 모드)**

  * 샌드박스 앱 모델 + XAML. 새 개발은 보통 WinUI 3/Windows App SDK 권장.

* **크로스플랫폼**

  * **.NET MAUI**: C#/XAML로 Android/iOS/macOS/Windows 동시 타겟. Windows 쪽 렌더러는 WinUI 사용.
  * **React Native for Windows**: JS/TS + React로 Windows 네이티브(UI는 WinUI 기반).
  * **Electron**(웹 기술 기반), **Flutter for Windows**(크로스엔진)도 선택지.

* **디자인/웹/하이브리드**

  * **Fluent UI**: MS의 디자인 시스템(Win/웹/모바일 컴포넌트).
  * **WebView2**: 데스크톱 앱에 Edge(Chromium) 임베딩.

# 언제 무엇을 쓸까 (초간단 가이드)

* **C++ 네이티브·레거시 연동 많음** → MFC / 순수 Win32(+ Direct2D/DirectWrite)
* **현대적인 Windows 전용 데스크톱** → **WinUI 3 + Windows App SDK** (C# 또는 C++)
* **.NET 데스크톱, MVVM·바인딩 중요** → **WPF**
* **빠른 폼 개발, 단순 UI** → Windows Forms
* **하나의 코드로 Win+모바일** → **.NET MAUI**
* **React 생태계 활용** → React Native for Windows
* **웹 기술로 데스크톱** → Electron (+ 또는 WebView2 하이브리드)
