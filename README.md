# Zeta HTML Edit Control

C# WinForms HTML editor from Zeta Software GmbH (Uwe Keim) wrapping the .NET WebBrowser control for rich HTML editing. `HtmlEditControl` (namespace `ZetaHtmlEditControl`) extends `ExtendedWebBrowser` with MSHTML `IDocHostUIHandler` hosting, clipboard paste (including paste-as-text), table/cell property forms, an HTML source editor, German (`.de.resx`) localisation, and a loopback preview `WebServer` over `HttpServer.dll`. `HtmlEditUserControl` adds a formatting toolbar around the same editor. This is Dave Robinson's working copy of the third-party Zeta control (assembly 1.1.0.3, copyright 2006-2009); there is no separable VaderConsulting wrapper in this tree.

**Source last updated:** 2013-08-23 · **Language:** C# · **Target:** .NET Framework 3.5 · **Output:** class library (`ZetaHtmlEditControl.dll`) + WinForms test exe (`Test.exe`)

## Solution structure

| Project | Language | Type | Purpose |
|---------|----------|------|---------|
| `Control` (`Control/Control.csproj`) | C# | Class library (`ZetaHtmlEditControl`) | Signed WinForms HTML editor: `HtmlEditControl`, `HtmlEditUserControl`, table/cell/source dialogs, `IExternalInformationProvider` / `IExternalWebServer`, German resources. |
| `Test` (`Test/Test.csproj`) | C# | WinForms exe (`Test`) | Host form that loads sample HTML, toggles the toolbar, and load/save `.html` files through `HtmlEditControl`. |
| `References` | binaries | Hint-path DLLs | `HttpServer.dll` (embedded preview server) and `SgmlReaderDll.dll` (SGML/HTML parse). |

`Control` is signed with `ZetaHtmlEditControl.snk` (`SignAssembly` true). Release AnyCPU output path is `..\..\Bin\Release\`. The solution lists only `Release|Any CPU`. `Test.csproj` still references `Properties\Settings.settings`, which is not in this dump (generated `Settings.Designer.cs` is present).

## How to open

Open `ZetaHtmlEditControl.sln` in Visual Studio 2012 or later (solution format 11.00 / Visual Studio 2012; `.csproj` ToolsVersion 4.0, originally ProductVersion 9.0.21022 / VS 2008). Both projects target .NET Framework 3.5 and need Windows Forms plus COM `Microsoft.mshtml`. Build `Control` then `Test`.

## Requirements

- Visual Studio 2012, .NET Framework 3.5

## Attribution and provenance

Working copy from Dave Robinson's OneDrive Historical Dev folder `Zeta HTML Edit Control`.

- **Author:** Uwe Keim, Zeta Software GmbH (`http://www.zeta-sw.com`)
- **Assembly title / product:** Zeta Html Edit Control
- **Assembly description:** Rich HTML edit control
- **Assembly company:** Zeta Software GmbH
- **Assembly copyright:** Copyright © 2006-2009 Zeta Software GmbH
- **Assembly version:** 1.1.0.3 (`Control`); Test host 1.1.0.2
- **Designed for:** Zeta Helpdesk (comment on `HtmlEditControl`)
- **Upstream:** [UweKeim/ZetaHtmlEditControl](https://github.com/UweKeim/ZetaHtmlEditControl); Code Project article *Zeta HTML Edit Control*
- **Code comments:** dated notes by Uwe Keim (2006-2013); MIME map credit `hd@imos.net` (Hannes Dorbarth / Imos) kept as third-party attribution

VS 2012/2013 `.suo` files and `Control.csproj.user` were in the zip and are gitignored. `bin/` and `obj/` build outputs (including Surface Pro 3 copies of the signed DLL) are gitignored.

## License

Original **Code Project Open License (CPOL) 1.02** as published with the Code Project article. This repository does **not** relicense the tree as MIT. There is no separable Dave Robinson wrapper or sample. See `LICENSE` and `THIRD_PARTY_NOTICES.md`.
