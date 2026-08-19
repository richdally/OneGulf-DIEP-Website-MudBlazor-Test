# DIEP MudBlazor Website
## Overview
The **Disaster Impact Estimation Prediction (DIEP) Website** is a web application developed to communicate the objectives, methodology, and results of a research project focused on estimating disaster impacts using geolocated social media self-reports and machine learning. The website provides a high-level overview of the research and serves as a portal for interactive geospatial dashboards that allow users to explore disaster impact prediction results.

The website was developed using **.NET 9**, **ASP.NET Core Blazor**, **Blazor WebAssembly**, and **MudBlazor 8.15.0** The application combines a responsive web interface with embedded **ArcGIS Experience Builder** applications to provide access to interactive geospatial visualizations of project results.

---

## Website Content

The website is organized around three primary components.

### Home

The **Home** page provides a high-level overview of the DIEP research project, including its motivation, data, methodology, disaster impact prediction framework, visualization capabilities, and disaster impact downscaling.

The page is intended to introduce the research to both technical and non-technical audiences while directing users to the research paper, project repositories, and interactive geospatial results.

### Geospatial Dashboard Overview

The **Geospatial Dashboard Overview** page introduces the interactive mapping component of the project and provides access to the two ArcGIS Experience dashboards.

This page serves as the transition between the research overview and the interactive geospatial applications.

### Interactive Dashboards

Two dedicated dashboard pages are included in the application:

- **Dashboard 1** – Hosts the primary ArcGIS Experience dashboard.
- **Dashboard 2** – Hosts the secondary ArcGIS Experience dashboard.

---

## Disaster Impact Estimation Prediction Framework

The DIEP research framework uses geolocated social media self-reports as inputs to a machine learning-based disaster impact estimation system. The framework produces probabilistic predictions for FEMA-related disaster impact variables at the ZIP Code level.

The project also explores methods for increasing the spatial resolution of disaster impact predictions. The associated downscaling workflow refines ZIP Code-level predictions to smaller geographic units, including Census Block Groups, to support more localized analysis of potential disaster impacts.

Additional information about the downscaling methodology and implementation is available in the separate **Disaster Impact Estimation Downscaling** repository.

---

## Project Structure

The solution uses a two-project architecture. The `DIEP_MudBlazor` project is the main ASP.NET Core web application and references the `DIEP_MudBlazor.Client` project. The client project uses Blazor WebAssembly and contains the MudBlazor-based user interface.

```text
DIEP_MudBlazor/
│
├── DIEP_MudBlazor.sln
│
├── DIEP_MudBlazor/
│   ├── Components/
│   ├── Properties/
│   ├── wwwroot/
│   │   └── images/
│   ├── Program.cs
│   ├── appsettings.json
│   └── DIEP_MudBlazor.csproj
│
├── DIEP_MudBlazor.Client/
│   ├── Layout/
│   │   ├── MainLayout.razor
│   │   └── NavMenu.razor
│   ├── Pages/
│   │   ├── Home.razor
│   │   ├── GeospatialDashboard.razor
│   │   ├── Dashboard1.razor
│   │   └── Dashboard2.razor
│   ├── Program.cs
│   └── DIEP_MudBlazor.Client.csproj
│
├── .gitignore
└── README.md
```

### Main Project — `DIEP_MudBlazor`

`DIEP_MudBlazor` is the main ASP.NET Core web project. It hosts the application, contains application configuration and server-side components, serves static resources, and references the client project.

Static images used by the website are stored in:

```text
DIEP_MudBlazor/wwwroot/images/
```

The main project targets **.NET 9** and references `Microsoft.AspNetCore.Components.WebAssembly.Server`.

### Client Project — `DIEP_MudBlazor.Client`

`DIEP_MudBlazor.Client` is the Blazor WebAssembly client project and contains the primary user interface for the website. This includes the Razor pages, shared layout, navigation system, and MudBlazor components.

Primary website pages are located in:

```text
DIEP_MudBlazor.Client/Pages/
```

Shared layout components are located in:

```text
DIEP_MudBlazor.Client/Layout/
```

The client project targets **.NET 9** and uses **MudBlazor 8.15.0**.

The main and client projects are two components of the same web application and should not be treated as independent websites.

---

## MudBlazor

[MudBlazor](https://mudblazor.com/) is used as the primary user-interface component library for the website. It provides reusable Blazor components for page layouts, navigation, typography, responsive grids, links, buttons, and other interface elements.

The website also supports **light and dark display modes**. Theme-responsive interface elements allow text and other components to adapt to the selected display mode.

---

## ArcGIS Experience Builder Integration

Interactive geospatial results are presented through **ArcGIS Experience Builder** applications embedded within dedicated Blazor pages.

The **Dashboard 1** and **Dashboard 2** pages act as containers for the ArcGIS experiences, allowing the research website and interactive mapping applications to function through a unified interface.

Changes to the underlying ArcGIS Experiences can generally be managed within ArcGIS Experience Builder without redesigning the surrounding Blazor website, provided that the associated application and embed locations remain valid.

---

## Running the Website Locally

### 1. Clone the Repository

```bash
git clone <repository-url>
```

### 2. Navigate to the Repository

```bash
cd DIEP_MudBlazor
```

### 3. Restore Project Dependencies

```bash
dotnet restore
```

### 4. Build the Solution

```bash
dotnet build
```

### 5. Run the Application

Using `dotnet watch`:

```bash
dotnet watch --project ./DIEP_MudBlazor/DIEP_MudBlazor.csproj
```

Alternatively, use:

```bash
dotnet run --project ./DIEP_MudBlazor/DIEP_MudBlazor.csproj
```

The terminal will display the local address where the application is being hosted. Open this address in a web browser to view the website.

`dotnet watch` is particularly useful during development because it monitors the project for changes while the local development server is running.

---

## Related Research Resources

For additional technical information about the DIEP framework, datasets, machine learning methodology, and model evaluation, refer to the associated research paper:

**Research Paper:** *Link forthcoming*

The disaster impact downscaling methodology and supporting implementation materials are available in the **Disaster Impact Estimation Downscaling** repository:

[Disaster Impact Estimation Downscaling](https://github.com/TAMIDSpiyalong/Disaster-Impact-Estimation-Downscaling)

---

## Repository Purpose

This repository preserves the source code and implementation structure of the DIEP research website. In addition to supporting continued development, the repository is intended to assist future researchers, developers, and project collaborators with understanding, maintaining, reproducing, and deploying the website.

