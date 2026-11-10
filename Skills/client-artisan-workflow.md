---
name: client-artisan-workflow
description: Production-ready workflow and strict standards for real-world client applications (Laravel, Tailwind CSS, Alpine.js/JS). Enforces token-efficient agent behavior, bulletproof validation, web security, rich UI/UX, robust database schemes, and clean code architecture. Trigger when building features, designing modules, database migrations, or UI layouts for client projects.
---

# Client Project Production & Efficiency Guidelines

This skill is the absolute standard for building enterprise-grade and production-ready client applications using **Laravel, Tailwind CSS, and JavaScript/Alpine.js**.

---

## 1. Token Efficiency & Agent Behavior Rules

* **No Unnecessary Testing Overhead:** Do not run automated test suites, browser environment testing, or repetitive debugging loops unless explicitly requested. If visual or data verification is needed, provide concise instructions for the user to verify directly.
* **Direct & Focused Execution:** Write or update code directly without creating temporary utility/test scripts that are not required in the production repository.
* **Minimal Commentary:** Avoid lengthy theoretical explanations in chat. Focus on code changes and brief summaries of completed features.

---

## 2. Module Development Workflow & Sequence

When building a module or system from scratch, always follow the correct dependency sequence:

1. **Foundational & Shared Modules First:** Build foundational reference tables first (e.g., `tahun_ajaran`, `users`, `roles`, `kategori`, `kelas`) before creating modules that depend on them (e.g., `siswa`, `transaksi`, `absensi`).
2. **Database & Schema Realism:**
   * Database schemas must reflect real-world business requirements (use `foreignId`, `softDeletes`, indexing on primary search columns, and precise data types).
   * Maintain consistent naming conventions across all tables.
3. **Backend Logic & Route Cleanliness:**
   * Use `Route::resource` or `Route::singleton` to keep route files clean.
   * Implement **Form Request Validation** to separate validation rules from Controllers.
   * Use **Service Layers** or **Actions** when business logic becomes complex, keeping Controllers thin.
4. **UI/UX Implementation:** Integrate responsive and feature-rich interfaces only after data logic is solid.

---

## 3. Data Validation & Error Handling Standards

* **Strict Input Validation:** 
  * Never trust incoming data. Implement rigorous validation rules on both frontend and backend.
  * Prevent type mismatch errors (e.g., ensure numeric fields strictly validate `numeric`/`integer`, string fields validate `string`, and IDs exist in the database via `exists:...` rules).
* **Robust Error Handling:**
  * Wrap complex database transactions in `DB::beginTransaction()` and `DB::rollBack()` with proper `try-catch` blocks.
  * Provide clean, user-friendly error messages or flash notifications; never expose raw SQL queries or stack traces to end users.

---

## 4. Web Security Best Practices

* **SQL Injection Prevention:** Always use Eloquent ORM or Query Builder parameter bindings. Avoid raw SQL queries unless strictly necessary, and never concatenate user input directly into queries.
* **Mass Assignment Protection:** Strictly define `$fillable` or `$guarded` properties on all Eloquent models to prevent unauthorized attribute injection.
* **Cross-Site Scripting (XSS) & CSRF:** 
  * Ensure all state-changing forms include `@csrf` directives.
  * Utilize Blade’s escaped syntax (`{{ $variable }}`) by default; only use unescaped syntax (`{!! $variable !!}`) when rendering trusted, sanitized HTML.
* **Authorization & Access Control:** Implement proper authorization checks using Laravel Policies or Gates to ensure users can only access data or perform actions they are permitted to.

---

## 5. Code Cleanliness & Commenting Standards

* **Necessary Comments Only:** Only write comments if the underlying logic is genuinely complex, non-standard, or handles specific business edge cases. Do not write comments that state the obvious (e.g., `// Save data to database`).
* **Clean Code:** Avoid logic duplication. Leverage Eloquent Scopes, Mutators/Accessors, and Traits wherever appropriate.

---

## 6. UI/UX & Feature Richness Standards (Anti-Flat UI)

Applications must feel **alive, intuitive, and functional**, rather than generic CRUD tables.

### A. Mandatory Index/Data Page Components (Beyond Basic Search/Filter)
Never deliver a plain table with just search and pagination. Professional data pages must include:
1. **Summary Cards / Metric Widgets (Top Section):** Display 3-4 key summary cards at the top of the table (e.g., Total Active Students, Late Today, Attendance Percentage).
2. **Quick Action Grouping:** Batch actions (e.g., *Bulk Delete*, *Export PDF/Excel*, *Batch Print ID Cards*).
3. **Empty States & Loading States:** Clean visual states when data is empty, complete with clear Call to Action (CTA) buttons.
4. **Interactive Status Badges:** Pill-style statuses with contrasting Tailwind color schemes (e.g., Green/Active, Red/Alpha, Yellow/Pending).

### B. Mobile First & Responsive Layout
* Ensure large tables are wrapped in `overflow-x-auto` or transformed into responsive **Card Layouts** on mobile viewports (`block md:hidden`).
* Interactive elements (buttons, inputs, dropdowns) must have comfortable touch targets for mobile devices (`py-2.5`, `px-4`).

---

## 7. UI Design Polish (Tailwind CSS)

* **Color Palette:** Use professional, modern SaaS color schemes (neutral Slate/Zinc paired with purposeful accents like Emerald, Indigo, or Violet).
* **Hierarchy & Depth:** Leverage subtle shadows (`shadow-sm`, `shadow-md`), clean borders (`border border-slate-200/60`), and clear section separation to prevent a monotonous UI.