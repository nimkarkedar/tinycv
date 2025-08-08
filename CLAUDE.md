# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

TinyCV is a single-page web application that provides AI-powered resume optimization. It's a client-side HTML application that allows users to upload PDF resumes, input job posting details, and generate mobile-optimized resumes and cover letters using the OpenAI API.

## Architecture

This is a standalone HTML file (`AI Resume Optimization Tool.html`) containing:
- Complete HTML structure with semantic markup
- Embedded CSS for responsive design and mobile-first layout
- Vanilla JavaScript for all functionality
- External CDN dependencies for PDF processing and document generation

### Key Components

1. **PDF Processing**: Uses PDF.js library for client-side PDF text extraction
2. **AI Integration**: Direct OpenAI API calls from the browser using user-provided API keys
3. **Document Generation**: HTML2Canvas + jsPDF for PDF export functionality
4. **UI/UX**: Mobile-first responsive design with drag-and-drop file upload

### External Dependencies

- PDF.js (v3.11.174) - PDF text extraction
- jsPDF (v2.5.1) - PDF generation
- html2canvas (v1.4.1) - Canvas rendering for PDF export
- OpenAI API - Text processing and optimization

## Development Commands

Since this is a single HTML file with no build process:

- **Run locally**: Open `AI Resume Optimization Tool.html` in a web browser
- **Test**: Manual testing through browser (no automated test suite)
- **Deploy**: Host the HTML file on any static web server

## Technical Considerations

### Security
- API keys are handled client-side only (not stored)
- CORS limitations require user input for job posting text (no direct web scraping)
- All processing happens in the browser

### Browser Compatibility
- Requires modern browser support for:
  - Fetch API
  - async/await
  - ES6+ features
  - Canvas API
  - FileReader API

### Mobile Optimization
- Responsive design with mobile-first approach
- Optimized resume templates specifically designed for mobile viewing
- Touch-friendly interfaces and interactions

## Code Structure

The single HTML file is organized into:
1. **Head section**: Meta tags, external script includes, embedded CSS
2. **Body structure**: Semantic HTML with form inputs and preview areas
3. **JavaScript**: Event handlers, API integration, PDF processing, and template generation

Key JavaScript functions:
- `extractPDFText()` - PDF processing
- `optimizeWithAI()` - OpenAI API integration
- `generatePreviews()` - Template rendering
- `downloadAsPDF()` - Export functionality