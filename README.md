# PackChecker - Legal Metrology (Packaged Commodities) Compliance Scanner

A cross-platform mobile application (**iOS & Android**) for scanning packaged commodity labels and validating statutory compliance under the **Legal Metrology (Packaged Commodities) Rules, 2011** (India) and its recent amendments.


---

## Key Features

1. **Rule 6 Statutory Checklist Verification**:
   - **Rule 6(1)(a)**: Name & complete address of Manufacturer / Packer / Importer with 6-digit postal PIN code.
   - **Rule 6(1)(b)**: Generic or common name of the commodity.
   - **Rule 6(1)(c) & Rule 10**: Net Quantity in standard SI symbols (`g`, `kg`, `ml`, `l`, `m`, `cm`, `mm`, `N`). Automatic detection and flagging of illegal non-standard abbreviations (`gms`, `Kgs`, `ML`, `c.c.`).
   - **Rule 6(1)(d)**: Month & Year of manufacture.
   - **Rule 6(1)(e)**: Maximum Retail Price (MRP) and mandatory `inclusive of all taxes` declaration.
   - **Rule 6(1)(da) / Rule 6(11)**: Mandatory Unit Sale Price (USP) per unit/g/kg/ml/l, including 1kg single-unit exemption logic.
   - **Rule 6(1)(f)**: Consumer care contacts (toll-free/phone, email, grievance nodal address).
   - **Rule 6(1)(g)**: Country of Origin declaration.
   - **Rule 6(1)(h)**: Best Before / Expiry date for food, cosmetics, and perishable items.
2. **Scanning Methods**:
   - **Live Camera Scanner**: Viewfinder with animated Principal Display Panel (PDP) framing guides, camera flip, and torch support.
   - **Multi-Panel Photo Upload**: Upload front, back, and MRP stamp panels together.
   - **1-Click Pre-Loaded Test Benchmarks**: Instant verification of compliant and non-compliant sample packaging.
3. **Dual Verification Engine**:
   - **Offline OCR Engine**: Built-in client-side Tesseract OCR + deterministic regex and rule parser. Works 100% offline.
   - **Optional Gemini Vision AI**: Connect your Google Gemini API key for zero-shot neural packaging analysis on curved, metallic, or stylized labels.
4. **Legal Risk & Audit Reporting**:
   - Dynamic 0-100% compliance scoring gauge.
   - Section 36 statutory penalty liabilities calculator (First offence up to ₹25,000, Second offence up to ₹50,000, compounding under Section 48).
   - Downloadable and printable **Official Statutory Compliance Audit Certificate (PDF / Print)**.
   - Digital **Rules Handbook** with Table 1 font size minimums, permitted metric units, and penalty provisions.
   - Local scan history database.

---

## Running the App

### Option A: Immediate Local & Mobile Testing (Browser & Local Wi-Fi)

To launch the local development server with mobile LAN access:

```bash
cd C:\Users\Daksh\.gemini\antigravity\scratch\lmpc-compliance-scanner
npm run dev -- --host
```

1. **On your PC**: Open `http://localhost:5173` in your browser.
2. **On iPhone (iOS)**:
   - Connect your iPhone to the same Wi-Fi.
   - Open Safari and navigate to `http://<YOUR-PC-IP>:5173`.
   - Tap the **Share** button -> select **"Add to Home Screen"**.
   - The app installs with full-screen native mobile feel and camera permissions!
3. **On Android Phone**:
   - Connect your Android phone to the same Wi-Fi.
   - Open Chrome and navigate to `http://<YOUR-PC-IP>:5173`.
   - Tap the **Menu (3 dots)** -> select **"Install App"** or **"Add to Home screen"**.

---

### Option B: Compiling Native iOS & Android Apps via Capacitor

This project is pre-configured with **Capacitor 8**:

#### Android (Generate APK / Android Studio):
```bash
npm run build
npm install @capacitor/android
npx cap add android
npx cap sync
npx cap open android
```
*Opens in Android Studio where you can build an APK or run directly on your connected Android device.*

#### iOS (Generate Xcode Project / IPA):
```bash
npm run build
npm install @capacitor/ios
npx cap add ios
npx cap sync
npx cap open ios
```
*Opens in Xcode on macOS for deployment to iPhone, Simulator, or TestFlight.*

---

## Automated Test Suite

To run the automated compliance test suite:
```bash
npx tsx scripts/test-engine.mjs
```
Verifies all statutory rules against compliant and non-compliant benchmark commodities.
