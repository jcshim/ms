**MS 추천 스택 + 템플릿**을 시나리오별

# 1) Windows 전용 데스크톱(현대 UX)

**스택**: **WinUI 3 + Windows App SDK**(C# 또는 C++)
**왜**: 최신 Windows 전용 UI, XAML·윈도우링·알림 등 신식 API 일원화. WPF/WinForms 후속 경로. ([Microsoft Learn][1])
**템플릿**

* Visual Studio: “**WinUI in Windows App SDK**” 템플릿
* CLI(프로젝트 생성은 VS 권장): `dotnet new tool-manifest` 후 필요 workload 설치 → VS로 생성/빌드
  **확장 전략**: WebView2로 웹 UI 끼워 넣기(하이브리드) ([Microsoft Learn][2])

# 2) .NET 데스크톱(데이터바인딩·MVVM 중심)

**스택 A**: **WPF (.NET 8/9)**
**왜**: MVVM·바인딩·리소스/스타일 체계가 탄탄. 대규모 LOB에 성숙. ([Microsoft Learn][3])
**템플릿**: `dotnet new wpf -n MyWpfApp`

**스택 B**: **Windows Forms**
**왜**: RAD 빠름, 유지보수·내부툴 다수.
**템플릿**: `dotnet new winforms -n MyWinFormsApp`

# 3) 크로스플랫폼(Win/Android/iOS/macOS)

**스택**: **.NET MAUI**
**왜**: 하나의 C#/XAML 코드베이스로 4대 플랫폼. Windows 쪽은 WinUI 기반 렌더러. ([Microsoft Learn][4])
**템플릿**

* `dotnet workload install maui`
* `dotnet new maui -n MyMauiApp`
  **변형**: **MAUI Blazor Hybrid**(웹 컴포넌트를 네이티브 셸에서 재사용) ([Microsoft Learn][5])

# 4) 웹/백엔드 + 데스크톱 연계

**스택**: **ASP.NET Core**(Razor Pages/MVC/Web API/Blazor)
**왜**: 빠르고 안전한 크로스플랫폼 웹앱/서비스 표준. ([Microsoft Learn][6])
**템플릿(예)**

* Razor Pages: `dotnet new webapp -n MyWeb` ([Microsoft Learn][7])
* Web API: `dotnet new webapi -n MyApi`
  **데스크톱 연계**: WebView2로 WPF/WinForms/WinUI에 웹 UI 임베딩. ([Microsoft Learn][8])

# 5) 자바스크립트 기반 네이티브 Windows

**스택**: **React Native for Windows**
**왜**: 조직에 React 역량이 있을 때 재사용 극대화(WinUI 기반 네이티브). ([Microsoft GitHub][9])
**템플릿(요지)**

* `npx react-native init MyApp` → `npx @react-native-windows/cli init --overwrite`(Windows 지원 추가)

# 6) 서버리스/이벤트 기반 백엔드

**스택**: **Azure Functions**(+ Event Grid/Service Bus/Cosmos DB)
**왜**: 인프라 최소화로 API·잡·Webhook·IoT 스트림 처리에 적합. ([Microsoft Learn][10])
**템플릿**

* `dotnet new func --name MyFunc`(또는 VS “Azure Functions” 템플릿)

# 7) 하이브리드 전략(점진적 현대화)

* **MFC/WPF/WinForms + WebView2**: 레거시 셸 유지, 신규 화면은 웹 또는 WinUI로 추가. ([Microsoft Learn][2])
* **WPF → WinUI 3 단계 전환**: 공용 로직 라이브러리화 → 신규 모듈 WinUI로 작성 → 병행 운영. ([Microsoft Learn][1])

---

## 빠른 추천 조합(현실 지향)

* **Windows 전용 신규**: **WinUI 3 + Windows App SDK**(+ WebView2) ([Microsoft Learn][1])
* **멀티 플랫폼 필요**: **.NET MAUI** 또는 **MAUI Blazor Hybrid** ([Microsoft Learn][4])
* **웹/클라우드 백엔드**: **ASP.NET Core Web API** + **Azure Functions(서버리스 보완)** ([Microsoft Learn][6])
* **React 역량 보유 조직**: **React Native for Windows**(필요 시 데스크톱은 WebView2 혼합) ([Microsoft GitHub][9])

[1]: https://learn.microsoft.com/en-us/windows/apps/winui/winui3/?utm_source=chatgpt.com "WinUI 3 - Windows apps"
[2]: https://learn.microsoft.com/en-us/microsoft-edge/webview2/?utm_source=chatgpt.com "Introduction to Microsoft Edge WebView2"
[3]: https://learn.microsoft.com/en-us/dotnet/desktop/wpf/?utm_source=chatgpt.com "Windows Presentation Foundation for .NET documentation"
[4]: https://learn.microsoft.com/en-us/dotnet/maui/what-is-maui?view=net-maui-9.0&utm_source=chatgpt.com "What is .NET MAUI? - .NET MAUI"
[5]: https://learn.microsoft.com/en-us/aspnet/core/blazor/hybrid/tutorials/maui?view=aspnetcore-9.0&utm_source=chatgpt.com "Build a .NET MAUI Blazor Hybrid app"
[6]: https://learn.microsoft.com/en-us/aspnet/core/?view=aspnetcore-9.0&utm_source=chatgpt.com "ASP.NET documentation"
[7]: https://learn.microsoft.com/en-us/aspnet/core/razor-pages/?view=aspnetcore-9.0&utm_source=chatgpt.com "Razor Pages architecture and concepts in ASP.NET Core"
[8]: https://learn.microsoft.com/en-us/microsoft-edge/webview2/landing/?utm_source=chatgpt.com "WebView2 documentation - Microsoft Edge"
[9]: https://microsoft.github.io/react-native-windows/docs/getting-started?utm_source=chatgpt.com "Get Started with Windows · React Native for Windows"
[10]: https://learn.microsoft.com/en-us/azure/azure-functions/functions-overview?utm_source=chatgpt.com "Azure Functions overview"
