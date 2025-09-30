# CustomBrowser

**A customized Chromium-based browser for Anatolia Solutions**

## Overview

CustomBrowser is a modified Chromium browser tailored for internal use at Anatolia Solutions. This project demonstrates the ability to adapt and extend a large-scale C++ codebase (Chromium) without prior experience in its architecture or language ecosystem.

## Key Modifications

### UI Customization
- **Rebranding**: Custom branding and visual identity throughout the browser interface
- **Integrated News Panel**: Built-in news feed display in browser panels
- **Custom Top/Side Panels**: Modified panel functionality with integrated tooling
- **Function Extensions**: Duplicated and modified existing Chromium functions to extend capabilities

### Security Architecture
Security controls are implemented at the infrastructure layer via NGINX:
- **GeoIP Filtering**: Geographic access restrictions based on IP location
- **Session Tracking**: Enhanced session monitoring and audit trails
- **Traffic Management**: Configured routing and access policies

## Technical Details

**Base**: Chromium (open-source browser engine)  
**Platform**: ARM64 Linux  
**Primary Language**: C++ (Chromium codebase)  
**Security Layer**: NGINX reverse proxy with custom configurations  

## Development Approach

This project required navigating Chromium's extensive codebase without prior knowledge of:
- Chromium's internal architecture
- C++ development conventions specific to the project
- Browser engine internals and rendering pipeline

Successfully identified relevant code sections, modified UI components, and extended functionality through reverse engineering and code analysis.

## Security Implementation

Security controls operate at the NGINX layer rather than within the browser itself:
```nginx
# Example configuration patterns (actual configs are proprietary)
geo $allowed_country {
    default 0;
    # GeoIP rules
}

# Session tracking
# Access logging with enhanced metadata
