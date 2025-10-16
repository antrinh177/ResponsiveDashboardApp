# Responsive Dashboard App - Technical Documentation
## Student Information
- **Name:** An Trinh
- **Student ID:** N01694520
- **Date Submitted:** October 16, 2025
- **Lab:** CPAN 213 - Lab 4
---
## Responsive Design Implementation
### Breakpoint Strategy
[Explain your breakpoint choices and rationale]
**Breakpoints Defined:**
- Small phones: < 350px width - 1 column layout
- Medium phones: 350-480px - 2 column layout
- Large phones: 480-768px - 2 column layout
- Tablets: 768-1024px - 3 column layout
- Large tablets: > 1024px - 4 column layout
**Design Decisions:**
The chosen breakpoints reflect common device widths across phones, tablets, and desktops. Small (≤350px) targets compact phones, medium (≤480px) for regular phones, large (≤768px) for large phones and small tablets, tablet (≤1024px) for standard tablets, and desktop (>1024px) for large screens.
### Grid System Implementation
The responsive grid dynamically adjusts the number of columns based on device type and orientation. Smaller screens use fewer columns to maintain clarity, while larger devices use more columns to take advantage of horizontal space.
**Column Calculation Logic:**
The getGridColumns() function determines the column count by first identifying the device type with getDeviceType() and checking whether the device is in portrait or landscape mode. Small/medium devices display 1–2 columns, large/tablets 2–3, and desktops 3–4, depending on orientation.
**Orientation Handling:**
Orientation changes are handled by updating screen dimensions using Dimensions.get('window').
### Typography Scaling
Font sizes are scaled using the rf() function, which calculates a responsive font size based on screen width and height.
**Scaling Formula:**
The formula in rf() multiplies the base font size by a scale factor derived from the screen width divided by 320 and screen height divided by 640, selecting the smaller of the two ratios. On iOS, the size is rounded; on Android, 2 pixels are subtracted for visual consistency.
**Typography Scale:**
- h1: [28]pt
- h2: [24]pt
- h3: [20]pt
- body: [18]pt
- caption: [14]pt
### Spacing System
[Document spacing scale and usage]
**Spacing Values:**
- xs: [1%]
- sm: [2%]
- md: [4%]
- lg: [6%]
- xl: [8%]
---
## Platform-Specific Implementations
### iOS Specific Styling
[List iOS-specific styles used]
- Shadow implementation using shadowColor, shadowOffset, shadowOpacity
- Border radius preferences
- Status bar height adjustments
### Android Specific Styling
[List Android-specific styles used]
- Elevation for shadows
- Material Design color scheme
- Status bar translucent handling
---
## Component Architecture
### Widget System Design
[Explain the BaseWidget pattern and reusability]
### Component Hierarchy
DashboardScreen
├── DashboardHeader
│ ├── Menu Button
│ ├── Title/Subtitle
│ └── Notification/Profile Buttons
├── ResponsiveGrid
│ └── StatisticWidgets (4x)
└── BaseWidget
└── Quick Actions (4x)
---
## Performance Optimizations Applied
### StyleSheet Optimization
[List specific StyleSheet optimizations]
- Used StyleSheet.create() for all styles
- Avoided inline styles where possible
- Pre-calculated style objects for variants
### Render Optimization
[Document re-render prevention strategies]
- Memoization of expensive calculations
- Proper key props on mapped components
- Conditional rendering optimization
### Performance Measurements
[Include actual FPS measurements]
- Scrolling: [60.0] FPS
- Orientation change: [57.9] FPS
- Widget interaction: [60.0] FPS
- Pull-to-refresh: [59.9] FPS
---
## Challenges Encountered and Solutions
### Challenge 1: [Challenge Title]
**Problem:** Icons were not displaying properly 
**Solution:** 
1/Opened the react-native.config.js file in the project root directory and added the asset path:
module.exports = {assets: ['./node_modules/react-native-vector-icons/Fonts'],};
2/Executed the command npx react-native-asset to link the icon font assets correctly.
3/Rebuilt the app to apply the changes.
**Learning:** Double-check that third-party libraries are properly linked and configured. Even if the installation seems to work, things like missing icons can happen if the native assets are not set up correctly.
---
## Testing Results
### Device Testing Matrix
| Device Type | Screen Size | Orientation | Columns | Result |
|-------------|-------------|-------------|---------|--------|

| Pixel 4 | 412x915 | Portrait | 1 | ✅ Pass |
| Pixel 4| 412x915 | Landscape | 1 | ✅ Pass |
| Pixel Tablet | 1600x2560 | Portrait | 2 | ✅ Pass |
| Pixel Tablet | 1600x2560 | Landscape | 4 | ✅ Pass |
### Functionality Testing
- [ ] Responsive grid adjusts to screen size ✅
- [ ] Orientation changes handled correctly ✅
- [ ] Pull-to-refresh works smoothly ✅
- [ ] All widgets display correctly ✅
- [ ] Platform-specific styling applied ✅
- [ ] Performance maintained at 60fps ✅
- [ ] Accessibility labels present ✅
- [ ] No console errors or warnings ✅
---
## Code Quality Checklist
- [ ] All components properly commented ✅
- [ ] Consistent naming conventions used ✅
- [ ] No unused imports or variables ✅
- [ ] Proper file organization ✅
- [ ] ESLint rules followed ✅
- [ ] Code formatted with Prettier ✅
- [ ] No hardcoded values (using theme system) ✅
- [ ] Accessibility props included ✅
---
## Reflection
### What I Learned
Through this lab, I gained understanding of building responsive mobile applications that adapt across multiple devices and screen sizes: 
- How to define breakpoints and use utilities like wp(), hp(), and rf() to scale layouts, spacing, and typography proportionally. 
- Handling orientation changes and implementing adaptive grid layouts
- Platform-specific styling differences, such as iOS shadows versus Android elevation, and how to manage the status bar to maintain a consistent look.
### Skills Gained
- Responsive design for mobile applications
- Flexbox mastery for complex layouts
- Platform-specific styling techniques
- Performance optimization strategies
### Areas for Improvement
Need to gain more understanding about coding and try to do by myself.
### Application to Future Projects
These skills will help me build scalable, performant, and visually consistent mobile apps in future projects.
---
**End of Documentation**