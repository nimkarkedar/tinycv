# PDF Customization Requirements

## Overview
This document outlines requirements for implementing user-customizable font combinations and color schemes for PDF generation in TinyCV. The focus is on professional, elegant designs suitable for resumes and cover letters.

## Font Combinations

### 1. Professional Serif + Sans-serif Pairings

#### Classic Elegance
- **Heading Font**: Playfair Display (Serif)
- **Body Font**: Source Sans Pro (Sans-serif)
- **Google Fonts Import**: 
  ```css
  @import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;600;700&family=Source+Sans+Pro:wght@300;400;600&display=swap');
  ```
- **Use Case**: Legal, finance, consulting resumes

#### Modern Professional
- **Heading Font**: Lora (Serif)  
- **Body Font**: Open Sans (Sans-serif)
- **Google Fonts Import**:
  ```css
  @import url('https://fonts.googleapis.com/css2?family=Lora:wght@400;500;600&family=Open+Sans:wght@300;400;600&display=swap');
  ```
- **Use Case**: Corporate, business development, management roles

#### Traditional Corporate
- **Heading Font**: Cambria (Serif)
- **Body Font**: Calibri (Sans-serif)
- **Implementation**: System fonts (pre-installed on most devices)
- **Fallback**: Available in CSS font stacks
- **Use Case**: Conservative industries, government positions

#### Contemporary Clean
- **Heading Font**: Georgia (Serif)
- **Body Font**: Lato (Sans-serif) 
- **Google Fonts Import**:
  ```css
  @import url('https://fonts.googleapis.com/css2?family=Lato:wght@300;400;600&display=swap');
  ```
- **Use Case**: Design, marketing, creative industries

#### Sophisticated Modern
- **Heading Font**: Constantia (Serif)
- **Body Font**: Montserrat (Sans-serif)
- **Google Fonts Import**:
  ```css
  @import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;500;600&display=swap');
  ```
- **Use Case**: Tech, startups, modern businesses

### Typography Guidelines
- **Body Text Size**: 10-12pt for optimal readability
- **Header Size**: 14-16pt for section titles
- **Name/Title Size**: 18-22pt for maximum impact
- **Line Height**: 1.4-1.6 for comfortable reading
- **ATS Compatibility**: All fonts maintain readability when parsed by ATS systems

## Color Schemes

### 1. Sage Sophistication
- **Primary**: Sage Green (#A3A678)
- **Secondary**: Pearl Gray (#D5D7B9)  
- **Accent**: Cream Beige (#F5F5DC)
- **Text**: Dark Charcoal (#333333)
- **Background**: Off-White (#FAFAFA)
- **Personality**: Calm, professional, nature-inspired

### 2. Dusty Elegance  
- **Primary**: Dusty Rose (#DCA1A1)
- **Secondary**: Vanilla (#F0EBAD)
- **Accent**: Peach Cream (#F0D5A4)
- **Text**: Deep Brown (#2D2D2D)
- **Background**: Soft Ivory (#F8F6F0)
- **Personality**: Warm, approachable, sophisticated

### 3. Soft Professional
- **Primary**: Powder Blue (#B8C6E3)
- **Secondary**: Light Gray Blue (#E8F1F2)
- **Accent**: Pearl White (#F7F9FB)
- **Text**: Navy (#1E3A8A)
- **Background**: Pure White (#FFFFFF)
- **Personality**: Trustworthy, calm, professional

### 4. Fresh Modern
- **Primary**: Mint Green (#B2DFDB)
- **Secondary**: Sea Glass (#E0F2F1)
- **Accent**: Light Mint (#F1F8E9)
- **Text**: Forest Green (#2E7D32)
- **Background**: Cool White (#FCFCFC)
- **Personality**: Fresh, innovative, growth-oriented

### 5. Lavender Luxury
- **Primary**: Soft Lavender (#D1C4E9)
- **Secondary**: Blush Pink (#F3E5F5)
- **Accent**: Rose Quartz (#FCE4EC)
- **Text**: Deep Purple (#4A148C)
- **Background**: Lavender Mist (#F9F7FF)
- **Personality**: Creative, luxurious, artistic

### 6. Warm Neutral
- **Primary**: Warm Beige (#F5F5DC)
- **Secondary**: Linen (#FDF6E3)
- **Accent**: Champagne (#FAF0E6)
- **Text**: Coffee Brown (#3E2723)
- **Background**: Cream White (#FFFEF7)
- **Personality**: Timeless, stable, approachable

## Implementation Requirements

### HTML Structure Modifications
```html
<!-- Font Selection UI -->
<div class="customization-panel">
  <div class="font-selection">
    <label for="font-combo">Font Style:</label>
    <select id="font-combo">
      <option value="playfair-source">Classic Elegance</option>
      <option value="lora-opensans">Modern Professional</option>
      <option value="cambria-calibri">Traditional Corporate</option>
      <option value="georgia-lato">Contemporary Clean</option>
      <option value="constantia-montserrat">Sophisticated Modern</option>
    </select>
  </div>
  
  <div class="color-selection">
    <label for="color-scheme">Color Theme:</label>
    <select id="color-scheme">
      <option value="sage">Sage Sophistication</option>
      <option value="dusty">Dusty Elegance</option>
      <option value="blue">Soft Professional</option>
      <option value="mint">Fresh Modern</option>
      <option value="lavender">Lavender Luxury</option>
      <option value="beige">Warm Neutral</option>
    </select>
  </div>
</div>
```

### CSS Implementation
```css
/* Font Loading */
.font-playfair-source {
  --heading-font: 'Playfair Display', serif;
  --body-font: 'Source Sans Pro', sans-serif;
}

.font-lora-opensans {
  --heading-font: 'Lora', serif;
  --body-font: 'Open Sans', sans-serif;
}

/* Color Scheme Variables */
.color-sage {
  --primary-color: #A3A678;
  --secondary-color: #D5D7B9;
  --accent-color: #F5F5DC;
  --text-color: #333333;
  --bg-color: #FAFAFA;
}

.color-dusty {
  --primary-color: #DCA1A1;
  --secondary-color: #F0EBAD;
  --accent-color: #F0D5A4;
  --text-color: #2D2D2D;
  --bg-color: #F8F6F0;
}

/* Apply to resume elements */
.resume {
  font-family: var(--body-font);
  color: var(--text-color);
  background-color: var(--bg-color);
}

.resume h1, .resume h2, .resume h3 {
  font-family: var(--heading-font);
  color: var(--primary-color);
}
```

### JavaScript Implementation
```javascript
// Font and color application
function applyCustomization(fontCombo, colorScheme) {
  const resumeElement = document.getElementById('resume-preview');
  
  // Remove existing classes
  resumeElement.className = resumeElement.className.replace(/font-\S+|color-\S+/g, '');
  
  // Apply new classes
  resumeElement.classList.add(`font-${fontCombo}`, `color-${colorScheme}`);
  
  // Update PDF generation settings
  updatePDFSettings(fontCombo, colorScheme);
}

// Load Google Fonts dynamically
function loadGoogleFonts(fontCombo) {
  const fontLinks = {
    'playfair-source': 'https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;600;700&family=Source+Sans+Pro:wght@300;400;600&display=swap',
    'lora-opensans': 'https://fonts.googleapis.com/css2?family=Lora:wght@400;500;600&family=Open+Sans:wght@300;400;600&display=swap',
    // ... other combinations
  };
  
  if (fontLinks[fontCombo]) {
    const link = document.createElement('link');
    link.href = fontLinks[fontCombo];
    link.rel = 'stylesheet';
    document.head.appendChild(link);
  }
}
```

## Technical Considerations

### Performance
- **Font Loading**: Use `font-display: swap` for better user experience
- **Caching**: Leverage Google Fonts CDN caching
- **Fallbacks**: Provide system font fallbacks for all Google Fonts

### Accessibility
- **Contrast Ratios**: All color combinations meet WCAG AA standards (4.5:1 minimum)
- **Font Sizes**: Maintain minimum 10pt for body text
- **Readability**: All fonts tested for dyslexia-friendly characteristics

### Cross-browser Compatibility
- **Font Support**: Fallback to system fonts when Google Fonts unavailable
- **Color Support**: All hex codes compatible with older browsers
- **CSS Variables**: Provide fallbacks for browsers without CSS custom properties

### Mobile Optimization
- **Font Scaling**: Responsive font sizes using clamp() or media queries
- **Touch Targets**: Customization controls minimum 44px touch targets
- **Performance**: Minimize font loading impact on mobile connections

## User Experience Guidelines

### UI/UX Recommendations
- **Preview**: Real-time preview of font and color changes
- **Persistence**: Remember user preferences in localStorage
- **Defaults**: Set professional defaults (Georgia + Lato, Sage colors)
- **Accessibility**: Keyboard navigation for all customization controls

### User Testing Considerations
- Test font combinations across different resume lengths
- Validate color schemes in various lighting conditions
- Ensure ATS compatibility with all combinations
- Test PDF export quality with different fonts and colors

## Future Enhancements

### Phase 2 Features
- Custom color picker with professional palette suggestions
- Additional font weights (light, medium, bold)
- Font size customization within professional ranges
- Export settings memory across sessions

### Advanced Options
- Industry-specific color and font recommendations
- A/B testing different combinations
- AI-powered combination suggestions based on job type
- Integration with company brand guidelines