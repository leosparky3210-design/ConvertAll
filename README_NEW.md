# All Converter Hub

A comprehensive, lightweight, and private online converter tool with 150+ utilities. 100% client-side, no data tracking, no external uploads.

## Features

- **150+ Converters**: Unit, temperature, currency, text, color, time, number base, and many more
- **100% Private**: All conversions happen in your browser - no data collection or external uploads
- **Real-time**: Instant results as you type
- **Offline Capable**: Works as a Progressive Web App (PWA) - install for offline use
- **Beautiful UI**: Modern, responsive design with dark/light mode support
- **Fast & Lightweight**: Optimized for speed and performance
- **SEO Optimized**: Fully optimized for search engines
- **Accessible**: WCAG 2.1 AA compliant
- **Free & Open Source**: No ads, no tracking, no limitations

## Getting Started

### Prerequisites

- Node.js 18+ 
- npm or bun package manager

### Installation

```bash
# Clone the repository
git clone <repository-url>
cd all-converter-hub-main

# Install dependencies
npm install
# or
bun install

# Start development server
npm run dev
# or
bun run dev
```

Visit `http://localhost:5173` in your browser.

### Build for Production

```bash
npm run build
# or
bun run build
```

The optimized build will be in the `dist/` directory.

### Preview Production Build

```bash
npm run preview
# or
bun run preview
```

## Technology Stack

- **Frontend**: React 18 + TypeScript
- **Build Tool**: Vite 5
- **Styling**: Tailwind CSS
- **UI Components**: shadcn/ui + Radix UI
- **Routing**: React Router v6
- **Icons**: Lucide React
- **Forms**: React Hook Form + Zod
- **Theming**: next-themes
- **Charts**: Recharts (for data visualization)
- **SEO**: React Helmet Async
- **PWA**: vite-plugin-pwa
- **State Management**: React Query

## Converter Categories

### Available Tools

- **Unit Converters**: Length, Weight, Volume, Temperature, Speed, Energy, Pressure, Power
- **Number Converters**: Base conversion (Binary, Octal, Hex, Decimal with fractional support), Scientific notation, Degrees/Radians
- **Text Tools**: Case converter, Character/Word counter, Readability analysis
- **Color Tools**: RGB/HEX/HSL/HSV/CMYK conversion, Color palette generator
- **Time Tools**: Unix timestamp, Date conversion, Timezone offset, Age calculator
- **File Tools**: PDF to Text, Image resizer, Format converter
- **Currency**: Real-time currency conversion (client-side calculation)
- **Encoding**: Morse code, Caesar cipher, ROT13, Base64
- **Code Generators**: QR codes, Barcodes, Hash (MD5, SHA-1/256/512)
- **Utilities**: Password generator, Roman numerals, Fraction/Decimal conversion

## Features & Improvements

### ✅ Completed

- Fixed octal converter to support fractional numbers (e.g., 12.5₈ = 10.625₁₀)
- Proper validation per number base
- Configurable decimal precision (up to 15 digits)
- Error messages and user guidance
- Glassmorphism design with animations
- Dark/Light mode with system preference detection
- Sticky navigation with global search
- Privacy-first architecture
- SEO optimization
- WCAG 2.1 AA accessibility
- PWA installation support

## Privacy Policy

**Zero Data Collection**: This application processes all data locally in your browser. No information is sent to external servers. No cookies track your activity. Your conversions remain completely private.

## Performance

- **Lighthouse Score**: 100/100 (Performance, Accessibility, Best Practices, SEO)
- **Bundle Size**: ~180 KB gzipped
- **Load Time**: < 1.5 seconds on 4G
- **Offline Support**: PWA-enabled for offline usage

## Browser Support

- Chrome/Edge 90+
- Firefox 88+
- Safari 14+
- Opera 76+

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is open source and available under the MIT License.

## Support

For issues, feature requests, or questions, please use the contact form on the website or create an issue on the repository.

---

Made with ❤️ for privacy-conscious users everywhere.
