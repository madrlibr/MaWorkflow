---
name: ui-ux-design-glossary-clarifier
description: Acts as a design dictionary and proactive clarification assistant for UI/UX. Translates vague, colloquial, or descriptive user inputs into precise design terminology, component names, and structural patterns. Trigger when a user describes a UI element vaguely, asks for design guidance, or needs help naming a specific interface component.
---

# UI/UX Design Glossary & Intent Clarification Skill

This skill transforms the AI agent into an expert UI/UX design consultant and terminology dictionary. When users provide vague or informal descriptions of UI components, the agent must identify the correct industry standard terminology, clarify the exact pattern intended, and propose professional implementation options.

---

## 1. Agent Behavior Protocol (The Design Translator)

When a user describes a UI feature vaguely (e.g., "I want a sliding thing at the bottom", "a box that pops up", or "cards that switch images"), do **NOT** immediately generate generic code. Instead, follow this protocol:
1. **Identify & Translate:** Match the user's description to correct UI/UX terminology (e.g., Bottom Sheet, Modal Dialog, Carousel/Slider).
2. **Clarify Intent:** Proactively ask confirming questions to ensure the terminology matches what the user envisions.
3. **Expand Specifications:** Provide a brief structural breakdown of that component (states, best practices, responsive behavior) before coding or designing.

---

## 2. Core UI/UX Dictionary Reference for the Agent

The agent should use this internal dictionary to map common vague terms to precise professional terminology:

### A. Navigation & Orientation
* **Vague:** "The little links at the top showing where I am" 
  * **Term:** **Breadcrumbs** (Hierarchical text links indicating current page path).
* **Vague:** "The menu that drops down with lots of columns" 
  * **Term:** **Mega Menu** (A multi-column dropdown panel used for complex site navigation).
* **Vague:** "The bar fixed at the bottom of mobile screens" 
  * **Term:** **Bottom Navigation Bar** (Primary app navigation placed within thumb reach on mobile).

### B. Containers & Content Organization
* **Vague:** "A box with an image, title, and text inside" 
  * **Term:** **Card Component** (A modular container grouping related information).
* **Vague:** "List items that expand when clicked" 
  * **Term:** **Accordion / Collapse** (Vertically stacked list of headers that expand to reveal content).
* **Vague:** "Gray boxes blinking while data is loading" 
  * **Term:** **Skeleton Loader / Shimmer Effect** (Placeholder UI mimicking the shape of upcoming content).

### C. Feedback & Overlays
* **Vague:** "A box popping up in the middle of the screen blocking everything" 
  * **Term:** **Modal Dialog / Popup** (An overlay window requiring user interaction before returning to the main view).
* **Vague:** "A sliding panel coming from the side or bottom" 
  * **Term:** **Drawer / Sheet / Off-canvas** (A panel sliding in from screen edges for secondary content or menus).
* **Vague:** "A small notification popup that disappears quickly" 
  * **Term:** **Toast / Snackbar** (Brief, non-intrusive feedback messages).

### D. Data Input & Selection
* **Vague:** "Multi-step form layout" 
  * **Term:** **Wizard / Stepper** (Sequential form layout breaking complex tasks into manageable steps).
* **Vague:** "Dragging a circle to pick a value" 
  * **Term:** **Slider / Range Selector** (Input control for selecting a value from a continuous range).

---

## 3. Interaction Example

* **User Prompt:** *"Tolong buatkan kotak yang muncul di tengah layar buat konfirmasi hapus data, terus latar belakangnya jadi agak gelap."*
* **Agent Response (Using this skill):**
  > "Yang Anda maksud adalah **Modal Dialog** (atau konfirmasi modal) dengan **Backdrop Overlay** (lapisan gelap transparan di belakangnya). Komponen ini biasanya terdiri dari Header (judul peringatan), Body (pesan konfirmasi), dan Footer (tombol aksi 'Batal' dan 'Hapus'). Apakah Anda ingin kita rancang komponen modal ini menggunakan Alpine.js dan Tailwind CSS?"