# Software Design & Development Document (SDD) for the  Rubik’s Cube Solver App

## 1. Introduction

### 1.1 Purpose
This Software Design and Development Document (SDD) describes the technical design, architecture, and development approach for the Rubik’s Cube Solver App. It translates the Product Requirements Document (PRD), App Flow, and UI/UX documentation into an implementable software design.

### 1.2 Scope
This document covers:
* System architecture
* Core components and responsibilities
* Data models and logic flow
* High-level algorithms
* Development considerations

NB.The application supports a standard 3×3 Rubik’s Cube.

## 2. System Overview
### 2.1 Application Type
* Single-page web application 
* Designed for web and mobile browsers

### 2.2 Page Structure
The system uses three pages:
* Home (core solving functionality)
* About (informational)
* Guide (instructional)

NB. All computation and interaction logic is executed within the Home page.

## 3. System Architecture
### 3.1 High-Level Architecture
It has the following:
**Presentation Layer**

* UI components (cube display, buttons)
* Handles user interaction and feedback

**Application Logic Layer**

* Cube state management
* Input validation
* Step navigation control

**Solving Engine Layer**

* Processes cube state
* Generates solution steps
* Outputs move sequences

## 4. Component Design

### 4.1 UI Components

#### Home Page Components

* Start Section
* Cube Input Component
* Review Component
* Solution Navigator
* Completion Component

#### Shared Components

* Button controls
* Modal / dropdown panels
* Error message component



### 4.2 Cube Representation

* Cube is represented as a structured data model
* Each face contains 9 color values
* Internal format uses a consistent face order (e.g., U, D, L, R, F,)

### 4.3 State Management

* Stores:

  * Current cube state
  * Validation status
  * Solution steps
  * Current step index

State transitions occur when:

* User edits cube colors
* User confirms cube
* User navigates solution steps



## 5. Input Validation Design

### Validation Rules

* Each color appears exactly 9 times
* All six colors are present
* Cube configuration is physically solvable

NB. Invalid states trigger user-facing error messages.


## 6. Solving Logic Design

### 6.1 Solving Strategy

* Uses a deterministic solving algorithm for 3×3 cubes
* Produces a sequential list of standard cube moves
* Does not optimize for speed-cubing

### 6.2 Output Format

* Move notation (e.g., R, U’, F2)
* One move per step
* Linked to visual cube updates


## 7. Navigation & Flow Control

* Step-based navigation within Home page
* Buttons control progression between integrated sections
* No full page reloads during solving


## 8. Error Handling

### Error Types

* Incomplete input
* Invalid color distribution
* Impossible cube state

### Error Response

* Clear message displayed near relevant UI section
* Guidance provided to correct the issue


## 9. Development Considerations

### 9.1 Technology Stack
# Frontend
* Frontend framework:React
* JavaScript-
* HTML and CSS

# State Management
* React state or Context API(lightweight state handlinh)

# Solving Logic
* Javascript-based cube-solving algorithm
* Internal cube representaion using Arrays or objects

#Visualization
*2D or 3D cube rendering using Canvas

### 9.2 Project File Structure
```
root/
├── public/
│   └── index.html
│
├── src/
│   ├── components/
│   │   ├── CubeInput.js
│   │   ├── CubeReview.js
│   │   ├── SolutionViewer.js
│   │   ├── Completion.js
│   │   └── Controls.js
│   │
│   ├── pages/
│   │   ├── Home.js
│   │   ├── About.js
│   │   └── Guide.js
│   │
│   ├── logic/
│   │   ├── cubeModel.js
│   │   ├── validator.js
│   │   └── solver.js
│   │
│   ├── styles/
│   │   └── main.css
│   │
│   ├── App.js
│   └── index.js
│
├── package.json
└── README.md
```
---
### 9.3 Software Configuration
* Environment configuration via *.env* files
* Linting and formatting for code consistency
* Responsive design configuration for mobile and desktop
* Error logging via browser console during development
---

## 10. Testing Strategy

* Unit testing for cube validation logic
* Functional testing of solving steps
* UI testing for navigation and interactions

---

## 11. Deployment Strategy

### Mode of Deployment

* The application is deployed as a **static web application**
* Built Frontend assets are served via a web hosting platform

### Deployment Options
* GitHub Pages
* Netlify
* Vercel

### Deployment Process
* Source code pushed to a version control repository
* Automated build process generates production
* Hosting platform serves the application over HTTPS
 
---

## 12. Future Extensions (Design-Level Only)

* Improved animation system
* Modular solving engine for future cube sizes
* Enhanced visual feedback during steps

