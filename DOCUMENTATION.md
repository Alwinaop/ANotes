# ANotes - Technical Documentation

## Table of Contents

1. [Project Overview](#project-overview)
2. [Technology Stack](#technology-stack)
3. [Architecture](#architecture)
4. [Features in Detail](#features-in-detail)
5. [Component Structure](#component-structure)
6. [State Management](#state-management)
7. [Data Model](#data-model)
8. [Performance Optimizations](#performance-optimizations)
9. [Security Features](#security-features)
10. [Installation and Deployment](#installation-and-deployment)
11. [Future Roadmap](#future-roadmap)
12. [Conclusion](#conclusion)

---

## 1. Project Overview

**ANotes** is a modern, client-side note-taking application designed to offer a seamless and feature-rich experience while maintaining simplicity and high performance. 

### **Key Objectives**
- **Performance**: Fast loading and optimized operation on all devices.
- **Usability**: An intuitive interface with a responsive design.
- **Privacy**: Secure storage with encryption for user data.
- **Extensibility**: A modular architecture that facilitates future feature expansion.

---

## 2. Technology Stack

### **Core Technologies**

| Category        | Technology     | Version  | Purpose                                      |
|---------------|--------------|---------|---------------------------------|
| Framework      | React        | 18.3.1  | UI library for building interfaces |
| Build Tool     | Vite         | 5.4.2   | Fast and modern frontend build tool |
| Language      | TypeScript   | 5.5.3   | Type-safe JavaScript for robust code |
| State Management | React Context API | - | Manages state using built-in React features |
| Styling       | Tailwind CSS | 3.4.1   | Utility-first CSS framework |
| Animation     | Framer Motion | 12.5.0  | Library for smooth UI animations |
| Icons        | Lucide React  | 0.344.0 | Customizable icon set |

### **Development Tools**

| Tool        | Version  | Purpose |
|------------|---------|----------|
| ESLint     | 9.9.1   | Code quality and style enforcement |
| PostCSS    | 8.4.35  | CSS transformations and optimizations |
| Autoprefixer | 10.4.18 | Automatic CSS vendor prefixing |

### **Storage & Persistence**
- **localStorage**: Used for persistent storage of notes and settings.
- **In-memory State**: Handles temporary runtime operations.

---

## 3. Architecture

ANotes follows a modern component-based architecture to ensure scalability, maintainability, and performance.

### **High-Level Structure**
```
ANotes
├── Components (UI presentation layer)
├── Context (State management)
├── Types (TypeScript type definitions)
├── Hooks (Custom React hooks)
├── Utils (Utility functions)
└── Constants (Shared constant values)
```

### **Key Architectural Patterns**
1. **Component-Based Design**: Ensures modular and reusable UI components.
2. **Context + Hooks Pattern**: Facilitates efficient state management.
3. **Client-Side Storage**: Ensures a server-independent application.
4. **Type-Driven Development**: Enhances robustness through TypeScript.
5. **Responsive UI**: Ensures seamless experience across all devices.

---

## 4. Features in Detail

### **Core Note Management**
- Create and edit notes with a rich text editor.
- Delete and archive notes (automatic cleanup after 30 days).
- Responsive UI optimized for various screen sizes.

### **Organization & Productivity**
- Categorize notes using **tags**.
- Mark important notes as **favorites**.
- Secure **private notes** with encryption.
- **Smart search** capabilities.
- Dynamic filtering by various criteria.

### **Import & Export**
- Download notes as **TXT** or **PDF**.
- Customizable file naming options.

### **User Experience Enhancements**
- **Dark mode** support.
- Smooth animations with **Framer Motion**.
- **Keyboard shortcuts** for efficient navigation.

---

## 5. Component Structure

### **Primary Components**

| Component        | Purpose | Features |
|----------------|---------|----------|
| `App.tsx`      | Main application wrapper | Routes and global context providers |
| `NoteList`     | Displays available notes | Filtering, sorting, and note cards |
| `NoteCard`     | Individual note display | Preview, actions, and metadata |
| `NoteEditor`   | Note creation and editing | Rich text formatting |
| `NoteFilters`  | UI for filtering notes | Tag selection and search |
| `PrivateSpaceDialog` | Password management | Secure access setup |

### **Component Hierarchy**
```
App
├── NoteProvider (Context)
│   ├── NoteList
│   │   ├── NoteFilters
│   │   ├── NoteCard (multiple)
│   │   ├── NoteViewer (when active)
│   ├── NoteEditor (when active)
└── PrivateSpaceDialog (when active)
```

---

## 6. State Management

ANotes utilizes React’s Context API for global state management.

### **Primary State Variables**
- **Notes**: List of user-created notes.
- **Search Term**: Stores the current search input.
- **Selected Tags**: Filters notes by assigned tags.
- **Theme Mode**: Toggles between light and dark mode.
- **View Modes**: Controls private note visibility and trash view.

---

## 7. Data Model

### **Note Object Structure**
```typescript
interface Note {
  id: string;
  title: string;
  content: string;
  tags: string[];
  isFavorite: boolean;
  isPrivate: boolean;
  isDeleted: boolean;
  createdAt: string;
  updatedAt: string;
}
```

---

## 8. Performance Optimizations

- **Vite Build System** for fast development.
- **Lazy Loading** of components.
- **Memoization** to prevent unnecessary re-renders.
- **Hardware-accelerated animations** via Framer Motion.
- **Minimal Dependencies** for a lightweight bundle.

---

## 9. Security Features

- **Password-protected private notes**.
- **Client-side encryption** for sensitive content.
- **Strict Content Security Policy (CSP)**.
- **Input Sanitization** to prevent XSS vulnerabilities.

---

## 10. Installation and Deployment

### **Local Development**
```bash
git clone https://github.com/alexjoshva/ANotes.git
cd ANotes
npm install
npm run dev
```

### **Production Deployment**
```bash
npm run build
npm run preview
```
- Deploy via **Netlify, Vercel, or GitHub Pages**.

---

## 11. Future Roadmap

### **Planned Enhancements**
- **Rich Text Editing**
- **Collaborative Notes**
- **Mobile Apps (iOS & Android)**
- **Cloud Sync & Offline Support**

---

## 12. Conclusion

ANotes is a high-performance, secure, and extensible note-taking application built with modern web technologies. It prioritizes user experience, privacy, and scalability, with a strong roadmap for future improvements.

---

*Last updated: March 18, 2024*
