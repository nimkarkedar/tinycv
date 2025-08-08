# TinyCV 📄

AI-powered resume optimization tool that creates mobile-friendly resumes and cover letters tailored to specific job postings.

## Features ✨

- **PDF Upload & Text Extraction** - Upload your resume PDF and extract text automatically
- **AI-Powered Optimization** - Uses OpenAI GPT-4 to optimize your resume for specific jobs
- **Mobile-First Design** - Creates resumes optimized for mobile viewing
- **Cover Letter Generation** - Automatically generates personalized cover letters
- **PDF Export** - Download optimized resumes and cover letters as PDFs
- **Manual Input Fallback** - Enter resume text manually if PDF extraction fails

## How It Works 🔄

1. **Upload Resume** - Drag & drop or select your resume PDF
2. **Add Job Details** - Paste the job posting URL or description
3. **Enter API Key** - Provide your OpenAI API key
4. **Optimize** - AI analyzes and optimizes your resume for the specific job
5. **Download** - Get your mobile-optimized resume and cover letter as PDFs

## Technology Stack 🛠️

- **Frontend**: Pure HTML5, CSS3, JavaScript (ES6+)
- **PDF Processing**: PDF.js v5.4.54 for client-side text extraction
- **AI Integration**: OpenAI GPT-4 API for content optimization
- **PDF Generation**: jsPDF + html2canvas for export functionality
- **Architecture**: Single-page application, no backend required

## Setup & Usage 🚀

1. Clone the repository:
   ```bash
   git clone https://github.com/kedarnimkar/tinycv.git
   cd tinycv
   ```

2. Open `AI Resume Optimization Tool.html` in your browser

3. Get an OpenAI API key from [OpenAI Platform](https://platform.openai.com/api-keys)

4. Upload your resume, enter job details, and optimize!

## Features in Detail 📋

### PDF Text Extraction
- Uses PDF.js v5.4.54 for reliable text extraction
- Handles complex layouts with spatial positioning
- Fallback to manual input for problematic PDFs
- Support for multi-page documents

### AI Optimization
- GPT-4 powered resume tailoring
- Keyword optimization for ATS systems
- Mobile-friendly formatting
- Professional tone and structure

### Export Options
- High-quality PDF generation
- Mobile-optimized layouts
- Professional templates
- Instant download

## Browser Compatibility 🌐

- Chrome 60+
- Firefox 55+
- Safari 11+
- Edge 79+

## Security & Privacy 🔒

- All processing happens client-side in your browser
- API keys are not stored or transmitted to our servers
- No data retention or tracking
- PDF files processed locally

## Contributing 🤝

Contributions are welcome! Please feel free to submit a Pull Request.

## License 📜

MIT License - see [LICENSE](LICENSE) for details.

## Roadmap 🗺️

- [ ] Multiple resume templates
- [ ] Batch processing for multiple jobs
- [ ] Browser extension
- [ ] Integration with job boards
- [ ] Resume scoring and feedback

---

Built with ❤️ by [Kedar Nimkar](https://github.com/kedarnimkar)