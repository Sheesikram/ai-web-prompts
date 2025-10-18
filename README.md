# ai-web-prompts
Example prompt
You are a senior full-stack engineer assigned to build a modern web application from scratch.


## Objective

(explain object in couple of lines)


## Structure 

(be specific about tech stack and structure of project)


## Tasks

(define clear tasks by breaking down into smaller chunks)


## Output Requirements

(define what's expected)


## Notes

(any other required specifics)---------------------------------------
-------------------------------------------------------------------------------------------------------------------------------------------
prompting instructions 
You start with a general guideline so that AI thinks of itself like that one. 

For example, saying, 

> You are a senior full-stack engineer assigned to build a modern web application from scratch.
> 

That way, it’ll position itself more as full stack engineer than a generalist responding to your chat. 

Next, you specify

### Objective

Explain the goal of the feature or project in 1–2 lines. For example, 

> Build a minimal blog editor that supports markdown formatting and autosave.
> 

Not too long. This is only objective. Like a main headline of news. 

Then you specify, 

### Structure

Define the tech stack and structural decisions. For example, 

> Next.js 14 with App Router, TailwindCSS for styling, Better Auth for auth, PostgreSQL for DB, Drizzle ORM, etc.
> 

And finally, you very specifically define tasks

### Tasks

Break the job into logical chunks.

> Set up project with Tailwind and PostgreSQL with Drizzle ORM
Create `posts` table with `title`, `content`, `slug`, `created_at` 
Build markdown editor using `react-markdown` 
Add autosave feature
Render blog post at `/blog/[slug]`
> 

Right after that, you repeat yourself again and define

### Output Requirements

What do you expect the AI to return?

> Output the full React component and tell me where to put it.
> 

And for any other information, you can provide

### Notes

Any extra details or constraints? Mention them as Notes. For example, 

> Keep it minimal. Follow industry code guidelines and . Don’t use heavy packages.
>
------------------------------------------------------------------------------------------------------------------------
Create a Next.js app with TypeScript, ESLint, TailwindCSS, Better Auth, Neon PostgreSQL, Drizzle ORM, and Zustand. Also define a products table, seed sample Nike items, and render it on homepage that queries the DB with Drizzle and renders the list.
--------------------------------------------------------------------------------------------------------------------------------------------------------------
src/app/globals.css
@import "tailwindcss";

@theme {
  /* Dark shades */
  --color-dark-900: #111111;
  --color-dark-700: #757575;
  --color-dark-500: #aaaaaa;

  /* Light shades */
  --color-light-100: #ffffff;
  --color-light-200: #f5f5f5;
  --color-light-300: #e5e5e5;
  --color-light-400: #cccccc;

  /* Supporting colors */
  --color-green: #007d48;
  --color-red: #d33918;
  --color-orange: #d37918;

  /* Font family */
  --font-jost: "Jost", sans-serif;

  /* Heading sizes */
  --text-heading-1: 72px;
  --text-heading-1--line-height: 78px;
  --text-heading-1--font-weight: 700;

  --text-heading-2: 56px;
  --text-heading-2--line-height: 60px;
  --text-heading-2--font-weight: 700;

  --text-heading-3: 24px;
  --text-heading-3--line-height: 30px;
  --text-heading-3--font-weight: 500;

  /* Lead */
  --text-lead: 20px;
  --text-lead--line-height: 28px;
  --text-lead--font-weight: 500;

  /* Body */
  --text-body: 16px;
  --text-body--line-height: 24px;
  --text-body--font-weight: 400;

  --text-body-medium: 16px;
  --text-body-medium--line-height: 24px;
  --text-body-medium--font-weight: 500;

  /* Caption */
  --text-caption: 14px;
  --text-caption--line-height: 20px;
  --text-caption--font-weight: 500;

  /* Footnote */
  --text-footnote: 12px;
  --text-footnote--line-height: 18px;
  --text-footnote--font-weight: 400;
}

---------------------------------------------------------------
Landing Page Prompt
You are a senior full-stack engineer assigned to build a modern web application from scratch.

## 💼 Objective

Build three responsive UI components — a **Navbar**, a **Reusable Card**, and a **Footer** — based on provided designs. These components will be used across the application, so they must follow consistent styling, responsive layout, and adhere to the application's theme and type system.

## 🧰 Structure

- Use the tech stack present in project structure 
- Use typography and color palette defined in `src/app/globals.css`
- All icons and images to be pulled from the `public/` folder
- Folder Structure:
		/src
		├── components/
		│   ├── Navbar.tsx
		│   ├── Card.tsx
		│   ├── Footer.tsx

## ✅ Tasks

1. **Navbar**
 - Implement a responsive navigation bar
 - Include logo (from `/public`), links, and any mobile hamburger toggle
 - Use semantic HTML and accessibility best practices

2. **Reusable Card**
 - Create a generic card component accepting props (title, description, image, etc)
 - Support various use-cases of a shoe
 - Responsive and theme-compliant

3. **Footer**
 - Implement a footer with navigation links, social icons, and copyright
 - Should be responsive and mobile-first

4. **Styling**
 - Use Tailwind CSS for all styling
 - Match colors, fonts, spacing with what's defined in `globals.css`

5. **Code Quality**
 - Use TypeScript for all components
 - Ensure all components are properly typed and reusable
 - Follow DRY and modular principles

## 📦 Output Requirements

- 3 standalone components in `src/components/`:
	- `Navbar.tsx`
	- `Card.tsx`
	- `Footer.tsx`
- Responsive and fully styled
- Properly typed with props interfaces
- Using assets from `public/`
- Uses theme values from `globals.css`
- Code is clean, readable, and production-ready

## 📝 Notes

- Design reference has been attached (screenshots)
- No need to wire up actual links or logic, just focus on UI/UX
- Mobile-first responsiveness is critical
- Follow component naming conventions and file structure used throughout the app
----------------------------------------------------------------------------------------------------------
Homepage Starter (page.tsx)
import React from "react";
import { Card } from "@/components";

const products = [
  {
    id: 1,
    title: "Air Max Pulse",
    subtitle: "Men's Shoes",
    meta: "6 Colour",
    price: 149.99,
    imageSrc: "/shoes/shoe-1.jpg",
    badge: { label: "New", tone: "orange" as const },
  },
  {
    id: 2,
    title: "Air Zoom Pegasus",
    subtitle: "Men's Shoes",
    meta: "4 Colour",
    price: 129.99,
    imageSrc: "/shoes/shoe-2.webp",
    badge: { label: "Hot", tone: "red" as const },
  },
  {
    id: 3,
    title: "InfinityRN 4",
    subtitle: "Men's Shoes",
    meta: "6 Colour",
    price: 159.99,
    imageSrc: "/shoes/shoe-3.webp",
    badge: { label: "Trending", tone: "green" as const },
  },
  {
    id: 4,
    title: "Metcon 9",
    subtitle: "Men's Shoes",
    meta: "3 Colour",
    price: 139.99,
    imageSrc: "/shoes/shoe-4.webp",
  },
];

const Home = () => {
  return (
    <main className="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
      <section aria-labelledby="latest" className="pb-12">
        <h2 id="latest" className="mb-6 text-heading-3 text-dark-900">
          Latest shoes
        </h2>
        <div className="grid grid-cols-1 gap-6 sm:grid-cols-2 lg:grid-cols-3">
          {products.map((p) => (
            <Card
              key={p.id}
              title={p.title}
              subtitle={p.subtitle}
              meta={p.meta}
              imageSrc={p.imageSrc}
              price={p.price}
              badge={p.badge}
            />
          ))}
        </div>
      </section>
    </main>
  );
};

export default Home;
------------------------------------------------------------------------------------------
Auth UI Prompt
You are a senior full-stack engineer assigned to build a modern web application from scratch.

## 💼 Objective
Design and build fully responsive, styled authentication pages (Sign In and Sign Up) using a shared group layout. These pages must support email/password login, social sign-in buttons (Google and Apple), and follow the application’s theme and typography.

The design should take inspiration from the attached layout and adapt it into this application’s brand identity, following the theme and typography defined in `src/app/globals.css`.


## 🧰 Structure
- Use Next.js App Router and group layout feature for sign-in and sign-up pages.
- Respect existing theme and typography in src/app/globals.css.
- Folder structure:
	/src
	├── app/
	│   ├── (auth)/
	│   │   ├── layout.tsx ← shared layout
	│   │   ├── sign-in/
	│   │   │   └── page.tsx
	│   │   └── sign-up/
	│   │       └── page.tsx
	├── components/
	│   ├── AuthForm.tsx
	│   └── SocialProviders.tsx
	├── public/

## ✅ Tasks
- Create a layout in `/app/(auth)/layout.tsx` with proper structure, margins, and responsiveness.
- Put/Move everything else in `/app/(root)/layout.tsx` file which will have its own shared layout. 
- Ensure the design feels cohesive across both pages.
- Sign In and Sign Up pages should use common form components.
- Create email/password inputs.
- Add social sign-in buttons (Google, Apple) using icons from Lucide or public assets.
- Style all components with Tailwind CSS using the theme in `globals.css`.
- Make it Responsive.
- Design must work well across devices.
- Use mobile-first and accessible practices.

## 📦 Output Requirements
- `/sign-in` and `/sign-up` pages with shared layout
- Responsive, mobile-friendly, accessible forms
- Reusable form and provider components
- Assets must be sourced from `/public`

## 📝 Notes
- Keep UI modular and theme-aligned.
- Focus is only on frontend (UI). Auth logic will be implemented separately.
- Maintain clean code and proper folder structure.
----------------------------------------------------------------------------------------------------
Auth Backend Prompt
You are a senior full-stack engineer assigned to build a modern web application from scratch.

## Objective

Develop a robust and scalable authentication system for a Nike-style e-commerce application. The system should support both authenticated users and guests using Better Auth, enabling email-password login (no verification in MVP), session management, and smooth guest-to-user transitions during login/signup. This system must be modular, extensible, and production-ready.

## Structure

- **Stack**: PostgreSQL + Drizzle ORM + Next.js (App Router) + Better Auth
- **Auth**: Cookie-based session auth using Better Auth (`auth_session`) and guest session (`guest_session`)
- **ORM Setup**: Modular schema files using Drizzle ORM
- **Folder Structure**:
	```
	/lib
		/db
		└── /schema
		    ├── user.ts
		    ├── account.ts
		    ├── session.ts
		    ├── verification.ts
		    └── guest.ts
		    └── index.ts
	```

## Tasks

1. **Create Auth-Related Database Schemas** (PostgreSQL via Drizzle ORM)
 
 a. `user` table  
 - `id`: uuid (UUID, primary key)  
 - `name`: string (optional)  
 - `email`: string (unique, not null)  
 - `emailVerified`: boolean (default false, not null)  
 - `image`: string (optional)  
 - `createdAt`: Date (default now, not null)  
 - `updatedAt`: Date (default now, not null)  

 b. `session` table  
 - `id`: uuid (UUID, primary key)  
 - `userId`: uuid (foreign key to `user.id`, not null)  
 - `token`: string (unique, not null)  
 - `ipAddress`: string  
 - `userAgent`: string  
 - `expiresAt`: Date (not null)  
 - `createdAt`: Date (default now, not null)  
 - `updatedAt`: Date (default now, not null)  

 c. `account` table  
 - `id`: uuid (UUID, primary key)  
 - `userId`: string (foreign key to `user.id`, not null)  
 - `accountId`: string (used for both email-password and OAuth accounts, not null)  
 - `providerId`: string (e.g. "credentials", "google", not null)  
 - `accessToken`: string (optional)  
 - `refreshToken`: string (optional)  
 - `accessTokenExpiresAt`: Date (optional)  
 - `refreshTokenExpiresAt`: Date (optional)  
 - `scope`: string (optional)  
 - `idToken`: string (optional)  
 - `password`: string (used for credentials login, optional)  
 - `createdAt`: Date (default now, not null)  
 - `updatedAt`: Date (default now, not null)  

 d. `verification` table  
 - `id`: uuid (UUID, primary key)  
 - `identifier`: string (e.g. email, not null)  
 - `value`: string (token/code to verify, not null)  
 - `expiresAt`: Date (not null)  
 - `createdAt`: Date (default now, not null)  
 - `updatedAt`: Date (default now, not null)  

 e. `guest` table  
 - `id`: uuid (UUID, primary key)  
 - `sessionToken`: string (unique, not null)  
 - `createdAt`: Date (default now, not null)  
 - `expiresAt`: Date (for auto-expiry, not null)

2. **Use Secure, Cookie-Based Session Management**
 - Use `auth_session` cookie for authenticated users (Better Auth handles this)
 - Use `guest_session` cookie for guests with UUID sessionToken
 - Cookies should be `HttpOnly`, `Secure`, `SameSite=strict`, `path=/`, `7-day expiry`

3. **Enable Guest-to-User Migration**
 - On successful login/signup, migrate guest cart and related records to the user account
 - Remove `guest_session` cookie and associated DB record

4. **Use Next.js Server Actions**
- Implement all auth-related logic using Next.js Server Actions
- Create `signUp`, `signIn`, `signOut`, `guestSession`, `createGuestSession`, and `mergeGuestCartWithUserCart`
- Put all of these functions in `lib/auth/actions.ts` 

5. **Route Protection & Checkout Flow**
- All product pages, categories, and cart routes are publicly accessible.
- Users can fully browse and use cart features without signing in.
- When proceeding to checkout, if user is not authenticated:
  - Redirect them to sign in/sign up page.
  - After successful login or account creation, merge cart data, then redirect to checkout page.

6. **Security & Validation**
- Follow industry best practices for, Authentication flow, Secure session handling, Input sanitation and Error handling
- Use Zod for strict validation, On all server action inputs, user-provided form data, and API payloads where applicable
- Ensure type safety across the stack using TypeScript + Zod schemas


## Output Requirements

- Drizzle-compatible schema definitions for all tables listed above
- Type-safe fields with correct defaults and constraints
- Modular files per table
- Ready to use with Better Auth (must not rename required tables/fields)
- Reusable and consistent schema that can be extended in future (e.g., 2FA, roles)

## Notes

- This is the MVP setup: email-password login only, no verification yet
- OAuth and verification are planned post-MVP, so include schema support now
- Do not implement cart, products, or orders — only auth-related tables
- Use correct TypeScript types as expected by Drizzle ORM
- Follow Better Auth's required structure strictly for `user`, `session`, `account`, and `verification`
=----------------------------------------------------------------------------------------------
Database Schemas Prompt
You are a senior full-stack engineer assigned to build a modern web application from scratch.

## 💼 Objective

Design and implement robust, normalized **database schemas** using **Drizzle ORM** for a scalable eCommerce application. This includes user accounts, product catalog, filters, reviews, orders, and supporting features,  all aligned with industry best practices for long-term scalability and clean code architecture.

## 🧰 Structure

- Tech Stack:
  - **ORM**: Drizzle ORM
  - **Database**: PostgreSQL (hosted on Neon Serverless)
  - **Language**: TypeScript
  - **Validation**: Zod schema integration
- Folder & File Structure:
	/lib
	└── db
	    ├── schema/
	    │   ├── addresses.ts
	    │   ├── products.ts
	    │   ├── variants.ts
	    │   ├── categories.ts
	    │   ├── collections.ts
	    │   ├── orders.ts
	    │   ├── carts.ts
	    │   ├── reviews.ts
	    │   ├── filters/
	    │   │   ├── genders.ts
	    │   │   ├── colors.ts
	    │   │   ├── sizes.ts
	    │   └── index.ts

## ✅ Tasks

0. Clean already existing schemas from `lib/db/schema.ts` file and delete that file.  
1. **Define Schema Files**
 - Implement Drizzle ORM schemas for the following entities:
   - Addresses
     ```
		  id: uuid (pk)
		  user_id: uuid (fk -> user.id)
		  type: enum('billing', 'shipping')
		  line1: string
		  line2: string
		  city: string
		  state: string
		  country: string
		  postal_code: string
		  is_default: boolean
	  ```
   - Products
     ```
		  id: uuid (pk)
		  name: string
		  description: text
		  category_id: uuid (fk -> categories.id)
		  gender_id: uuid (fk -> genders.id)
		  brand_id: uuid (fk -> brands.id)
		  is_published: boolean
		  default_variant_id: uuid (nullable, fk -> product_variants.id)
		  created_at: timestamp
		  updated_at: timestamp
		 ```
   - Categories
     ```
		  id: uuid (pk)
		  name: string
		  slug: string (unique)
		  parent_id: uuid (nullable, fk -> categories.id)
     ```
   - Product Variants
     ```
		  id: uuid (pk)
		  product_id: uuid (fk -> products.id)
		  sku: string (unique)
		  price: numeric(10, 2)
		  sale_price: numeric(10, 2) nullable
		  color_id: uuid (fk -> colors.id)
		  size_id: uuid (fk -> sizes.id)
		  in_stock: int
		  weight: float
		  dimensions: jsonb  // { length, width, height }
		  created_at: timestamp
     ```
  - Product Images
     ```
		  id: uuid (pk)
		  product_id: uuid (fk -> products.id)
		  variant_id: uuid (nullable, fk -> product_variants.id)
		  url: string
		  sort_order: int default 0 // for gallery ordering
		  is_primary: boolean
     ```
   - Genders
     ```
		  id: uuid (pk)
		  label: string  // e.g., "Men"
		  slug: string   // e.g., "men"
     ```
   - Brands
     ```
		  id: uuid (pk)
		  name: string  // e.g.,  “Nike”, “Adidas”
		  slug: string   // e.g., "men"
		  logo_url: string // optional
     ```
   - Colors
     ```
		  id: uuid (pk)
		  name: string       // "Red"
		  slug: string       // "red"
		  hex_code: string   // "#FF0000"
		 ```
   - Sizes
     ```
		  id: uuid (pk)
		  name: string       // "M"
		  slug: string       // "m"
		  sort_order: int    // for ordering: S < M < L
		 ```
   - Reviews
     ```
			id: uuid (pk)
		  product_id: uuid (fk -> products.id)
		  user_id: uuid (fk -> user.id)
		  rating: int (1-5)
		  comment: text
		  created_at: timestamp
     ```
   - Carts
     ```
		  id: uuid (pk)
		  user_id: uuid (nullable, fk -> user.id) // for guests: null
		  guest_id: string (nullable, fk -> guest.id) // 
		  created_at: timestamp
		  updated_at: timestamp
     ```
   - Cart Items
     ```
		  id: uuid (pk)
		  cart_id: uuid (fk -> carts.id)
		  product_variant_id: uuid (fk -> product_variants.id)
		  quantity: int
     ```
   - Orders
     ```
		  id: uuid (pk)
		  user_id: uuid (fk -> user.id)
		  status: enum('pending', 'paid', 'shipped', 'delivered', 'cancelled')
		  total_amount: numeric(10, 2)
		  shipping_address_id: uuid (fk -> addresses.id)
		  billing_address_id: uuid (fk -> addresses.id)
		  created_at: timestamp
     ```
   - Order Items
     ```
		  id: uuid (pk)
		  order_id: uuid (fk -> orders.id)
		  product_variant_id: uuid (fk -> product_variants.id)
		  quantity: int
		  price_at_purchase: numeric(10, 2)
		 ```
   - Payments
     ```
		  id: uuid (pk)
		  order_id: uuid (fk -> orders.id)
		  method: enum('stripe', 'paypal', 'cod')
		  status: enum('initiated', 'completed', 'failed')
		  paid_at: timestamp
		  transaction_id: string (nullable)
     ```
   - Coupons
     ```
		  id: uuid (pk)
		  code: string (unique)
		  discount_type: enum('percentage', 'fixed')
		  discount_value: numeric
		  expires_at: timestamp
		  max_usage: int
		  used_count: int
     ```
   - Wishlists
     ```
		  id: uuid (pk)
		  user_id: uuid (fk -> user.id)
		  product_id: uuid (fk -> products.id)
		  added_at: timestamp
     ```
   - Collections
     ```
		  id: uuid (pk)
		  name: string       // "Summer '25"
		  slug: string       // "summer-25"
		  created_at: timestamp
     ```
   - Product–Collection relationships
     ```
		  id: uuid (pk)
		  product_id: uuid (fk -> products.id)
		  collection_id: uuid (fk -> collections.id)
     ```
 
2. **Data Modeling Best Practices**
 - Use accurate data types: `uuid`, `text`, `numeric`, `jsonb`, `timestamp`, `enum`, etc.
 - Define proper **foreign key relationships** using `relations()`.
 - Normalize the structure for referential integrity and scalability.
 - Include **constraints**: `unique`, `not null`, `default`, etc.
 - Use **snake_case** for database columns and **camelCase** in TypeScript.

3. **Validation & Typing**
 - Use Zod validation for each table.
 - Create proper enums and use them into the relevant schemas.

4. **Maintainability**
 - Keep schema files modular and readable.
 - Group related entities (e.g. `filters/`) logically.
 - Ensure compatibility with `drizzle-kit` migration tools.
 - Design to support future use in APIs (REST/tRPC), admin dashboards, and internal tooling.
 
5. **Seed**
	- Study the product-related schema (including any product, product_variants, categories, etc. that were or will be defined).
	- Create a `seed.ts` function that populates the database with 15 realistic Nike products with variants
	- Seeds filters (genders, colors, sizes), brand(s), categories, collections
	- Seed data should reflect proper foreign key relationships and follow any constraints
	- For each product randomize colors, multiple sizes, multiple variants and images per variant/color (for few).
	- Upload images from `public/shoes` to server using `fs` as static images to `static/uploads/...`
	- Log progress and errors clearly
	- Add `db:seed` script to `package.json`

## 📦 Output Requirements

- Fully typed Drizzle ORM schema definitions per table
- Zod-based validation for each insert/select
- Foreign keys and relations defined with `relations()`
- Clean file separation and index export
- Ready for production with no placeholder/mocked data

## 📝 Notes

- This will power a production-grade system.
- Focus on scalability, modularity, and clarity.
- Don’t include dummy data or test code.
- Code must be clean, reusable, and aligned with modern TypeScript best practices.
==============================================================================================
Product Listing Page Prompt

You are a senior full-stack engineer assigned to build a modern web application from scratch.

## Objective

Build a **Product Listing Page** for a Nike e-commerce web app that supports filterable, sortable product listings. Product data must render **server-side** using URL query parameters. The filter & sort UI must be built using **client-only components** that sync state to the URL, without performing any data fetching themselves.

The design should take inspiration from the attached layout and adapt it into this application’s brand identity, following the theme and typography defined in `src/app/globals.css`.

## Structure

* Use **Next.js App Router**.
* Use **`query-string`** for parsing and stringifying query parameters.
* Use **Next.js** for routing & shallow updates (do not use the `URLSearchParams` API directly).
* Query-related helpers must live in `/lib/utils/query.ts`.
* Keep logic modular: separate client components for `Filters.tsx` and `Sort.tsx`.
* Existing UI components like `Card.tsx` must be reused.
* Use Tailwind CSS, respecting global theme from `/src/app/globals.css`.
* Folder Structure

	```
	/src
	├── app/
	├── (root)/
	│   └── products/
	│       └── page.tsx              ← server-rendered product listing
	├── components/
	│   ├── Filters.tsx               ← client-only filters
	│   ├── Sort.tsx                  ← client-only sort
	│   └── Card.tsx                  ← reused product card
	├── lib/
	│   └── utils/
	│       └── query.ts              ← helpers for parsing/stringifying URL filters
	```

## ✅ Tasks

- 1. **Server-Rendered Product Page**

  * Read filter/sort state from `searchParams`.
  * Use helper functions from `/lib/utils/query.ts` to parse query params.
  * Filter and sort mocked product data accordingly (no data fetching. Use images from `/public` folder)
  * Render a responsive grid of `Card` components with filtered results.
  * Show active filters (e.g., badges like “Men”, “Red”, “Size: M”).

- 2. **Filters UI (`Filters.tsx`)**

	Build a **client-only** sidebar/drawer component:

  * Filter groups: Gender, Size, Color, Price Range (should be checkboxes).
  * Each group supports **multi-selection** with checkboxes.
  * Clicking a selected filter **removes** it from the URL.
  * Must use `query-string` npm package to **read and update URL filters**.
  * Must use **Next.js routing for URL params update**.
  * Reads initial state from URL and updates it without full reload.
  * **Responsive**:
    * Sidebar on desktop.
    * A collapsible filter drawer that slides in from the left on mobile devices, appearing above the product page with a semi-transparent overlay for focus.
  * Expands/collapses filter groups.
  * Styled with Tailwind while strictly respecting `src/app/globals.css` style theme

- 3. **Sort UI (`Sort.tsx`)**
	
	* Build a **client-only** dropdown or button group.
  * Options: Featured, Newest, Price (High → Low), Price (Low → High).
  * Sort state must sync to URL query param (e.g., `?sort=price_desc`).
  * Use `query-string` with Next.js routing.
  * Also resets pagination to page 1 on sort change.

- 4. **Query Utilities (`/lib/utils/query.ts`)**
	
	* Write reusable functions for updating and removing URL params.
	* Must use `query-string` package.
	* These should be pure functions (easy to test).

- 5. **Navigation Links**

	* Other pages (e.g., category navigation like “Men”) must link to `/products?gender=men`.
	* Clicking those links must pre-apply filters server-side and reflect them in UI.

- 6. **Responsiveness**

	* **Entire layout must be mobile-first and fully responsive**.
	* Filters collapse into drawer on small screens.
	* Use Tailwind utility classes (no inline styles unless strictly necessary).
	* Whole layout should respect max width structure as all other pages. It should be uniform in structure. 

- 7. **URL & State Sync**

	Filter/Sort UI should:
  * Stay in sync with URL query string.
  * Work with browser back/forward.
  * Clear filters via UI and update URL accordingly.
  * Emit filter changes that cause shallow navigation.

- 8. **Accessibility**

	* Use semantic HTML.
	* Keyboard-navigable filter checkboxes.
	* Visibly focused states.

## 📦 Output Requirements

- A fully functional server side rendered `/products` page:
	* Filters, sort options, and URL sync working end-to-end.
	* Responsive design with sidebar/drawer behavior.
- `Filters.tsx` and `Sort.tsx` implemented as isolated client-only components.
- `lib/utils/query.ts` utility with tested, modular URL-handling functions.
- All UI interactions update the URL and rerender data accordingly.
- Clean, maintainable code with modular structure and component reuse.
- Handle empty state gracefully if no products match filters.

## 📝 Notes

* No real backend integration; mocked data only.
* Filters should apply **immediately** on change (no Apply button).
* Refer to Next.js 15 way of reading values from searchParams
* Product cards should reflect active filters (e.g., show gender or color tags).
* Placeholder product data must mirror actual schema (refer to product structure + variants).
* Study the DB architecture provided separately before writing the seed function to match.
-----------------------------------------------------------------------------------------------
Product Actions Prompt
## 💼 Objective
Implement a high-performance backend server action to fetch products with full filtering, search, sorting, and pagination support.

This will power the product listing page of the e-commerce platform, optimized for server-side rendering and SEO.

## ⚙️ Structure

- Use Next.js Server Actions with Drizzle ORM and PostgreSQL
- Place main logic in `/src/lib/actions/product.ts`
- Place query parsing helpers in `/src/lib/utils/query.ts`
- Query should support product variants, color-specific images, and generic images
- Render products server-side using `/src/components/Card.tsx`

All queries must be optimized to minimize joins and avoid N+1 queries


## ✅ Tasks

1. **Implement getAllProducts**

	- Accept a params object supporting:
		- Search (search)
		- Filters
		- Price range (priceMin, priceMax)
		- Sorting (sortBy=price_asc, sortBy=latest, etc.)
		- Pagination (page, limit)
	- Apply all filters and sorting in a single Drizzle ORM query
	- Ensure images are fetched in the same query
	- Return:
		- products: Product[] (with aggregated minPrice, maxPrice, and top images)
		- totalCount: number

2. **Implement getProduct**

	- Accept a `productId`
	- Fetch full details:
		- All product fields
		- Variants (with stock, size, color, price)
		- Category, Brand, Gender
		- All images
	- Ensure one query is used where possible with relations

3. **Update `/src/app/(root)/products/page.tsx`**

	- Make page.tsx a server component with an async function
	- Await searchParams before using their values
	- Parse filters using `/src/lib/utils/query.ts`
	- Call `getAllProducts(params)` and map results into Card components

4. **Create Query Utils in `/src/lib/utils/query.ts`**

	- `parseFilterParams(searchParams)` → maps URL params to a filters object
	- buildProductQueryObject(filters) → builds a Drizzle query object
	- Handle defaults & missing values gracefully


## 📦 Output Requirements

- `getAllProducts(filters)` returns correct product list with all filters applied
- `getProduct(productId)` returns complete details for PDP
- `/products/page.tsx`:
	- Waits for searchParams
	- Uses parsed params to call getAllProducts
	- Renders server-side with Card
- Must return color-specific images if color filter applied, otherwise return generic images
- Must be responsive and use `/src/app/globals.css`


## 📝 Notes

- Use compound indexes for (brand_id, is_published), (category_id, is_published), (color_id, product_id) for performance
- Avoid loops. Use joins and aggregations
- Default sort: created_at DESC
- Make it future-proof for different scenarios
- Pagination must prevent over-fetching
- Ensure TypeScript types are explicit
===================================================================================
Product Details Page Prompt

You are a senior full-stack engineer assigned to build a modern web application from scratch.

## Objective

Build a **Product Details Page** UI for a Nike e-commerce app that renders a rich product gallery, color/size selectors, and product metadata. The page must be **pixel-perfect** to the attached desktop design and **strictly responsive across mobile and tablet devices**. It should open when a user clicks any product card and feel **uniform** with the rest of the site.

⚠️ **Strict Requirement**: The entire page must be **server-rendered**. Only interactions and dynamic UI parts that require client-side state (gallery, swatches, size picker) must be placed in isolated client components under `/components`.

⚠️ **Strict Requirement**: Follow the provided design screenshots **exactly**. No deviations. Do gallery, collapsible section, product information UI as is. Strictly follow same layout. 

⚠️ **Strict Requirement**: Code must be **super clean, modular, and easy to understand** — use clear file/variable names and maintain a clean separation between server and client components.

## Structure

* **Framework**: Next.js App Router with server components.
* **Dynamic route**: `src/app/(root)/products/[id]/page.tsx` (server-rendered entrypoint).
* **UI-only**: use **mocked product data** (no fetching, no DB, no cart/favorite logic).

  * Use static images from `/public` for now.
* **Icons**: use **lucide-react** consistently.
* **Styling**: Tailwind CSS; strictly follow `src/app/globals.css` (no inline styles).
* **Component structure**:

  ```
  /src
  ├── app/
  │   └── (root)/
  │       └── products/
  │           └── [id]/
  │               └── page.tsx          ← server-rendered product detail page
  ├── components/
  │   ├── ProductGallery.tsx            ← client (gallery UI + swatches)
  │   ├── SizePicker.tsx                ← client (size selector)
  │   ├── CollapsibleSection.tsx        ← client (details/shipping/reviews)
  │   └── Card.tsx                      ← reuse for “You Might Also Like”
  ```

## ✅ Tasks

1. **Server-Rendered Page**

   * Implement `/products/[id]/page.tsx` as a **server component**.
   * Read `{ params: { id } }` to load static mock product data.
   * Compose the page using smaller modular components.

2. **Product Gallery (Client Component)**

   * Main image + thumbnail strip per design.
   * Strict image guards:

     * Render only if at least one valid image exists.
     * First valid image is default main image.
     * Auto-skip broken images; fallback to `ImageOff` Lucide icon with empty state.
   * Keyboard accessible (arrow keys + focusable thumbnails).

3. **Color & Variant UI (Client Component)**

   * Show color swatches for variants with valid images.
   * Selecting a swatch updates the gallery to that variant.
   * Use Lucide icons (e.g., `Check`) for selection indicators.

4. **Size Picker (Client Component)**

   * UI-only dummy sizes.
   * Visual toggle only, no backend/state.
   * Accessible with keyboard navigation.

5. **Product Metadata (Server Rendered)**

   * Title, price, compare-at price, discount badge, description/specs.
   * “Add to Bag” and “Favorite” = **static UI only** (no handlers).
   * Use Lucide icons (`Heart`, `ShoppingBag`, `Star`).

6. **“You Might Also Like” Section**

   * Server-rendered grid of static products using `Card.tsx`.
   * Each card links to `/products/[id]` via `next/link`.
   * Apply the same image guard rules (no broken `<img>`).

7. **Navigation**

   * Ensure product cards across the app route to this page correctly.

8. **Responsiveness**

   * **Desktop**: match desktop screenshot **exactly**.
   * **Mobile/Tablet**: follow attached screenshot layout **strictly**:

     * Main product image on top.
     * Thumbnails scrollable below (horizontal overflow only for gallery).
     * Rest of content stacked in a clean, single-column layout.
   * Use existing breakpoints/utilities in `globals.css`.

9. **Accessibility**

   * Semantic HTML, alt text, focus styles.
   * Swatches and thumbnails keyboard navigable with visible focus rings.

10. **Empty/Skeleton States (UI-Only)**

* Skeleton placeholders for gallery + text.
* Graceful fallbacks for missing images with `ImageOff` icon.
* Rest of content should always render even if gallery is empty.

11. **Collapsible Sections (Client Component)**

* “Product Details” → dummy text.
* “Shipping & Returns” → dummy text.
* “Reviews” → empty state.

## 📦 Output Requirements

* A production-ready, **server-rendered** product details page in `page.tsx`.
* Pixel-perfect desktop layout and strict adherence to mobile/tablet screenshots.
* Gallery/variants/sizes as client components in `/components`.
* Super clean, modular code with clear naming and separation.
* Uses **lucide-react** for all icons.
* Uniform styling with `globals.css`.
* No data fetching, DB work, or business logic — **UI only**.

## 📝 Notes

* Prefer `next/image` with width/height + `sizes` to avoid CLS.
* Keep components focused and reusable.
* Absolutely no inline styles; follow global theme tokens.
* **Strictly follow the provided design screenshots**. Do not deviate.
* Maintain **clear separation of concerns** between server and client
=================================================================================================
Product Detail Integration Prompt
You are a **Senior Full-Stack Engineer** tasked with integrating backend product data into a fully responsive Product Details Page with flawless image handling and consistent UI.

## 💼 Objective

Build a **fully integrated Product Details Page (PDP)** in a Nike e-commerce app using **real backend data** from existing schemas.
The PDP must:

* Fetch the correct product when a user clicks a product card.
* Show **reviews** and **recommended products** via **server actions** wrapped in `Suspense` (non-blocking).
* Handle product → variant → image relations **correctly** (no shortcuts or buggy logic).
* Gracefully render a **Not Found** block if product doesn’t exist.

## ⚙️ Structure

* **Next.js App Router** with a **server component** page:
  `src/app/(root)/products/[id]/page.tsx`

* **Backend**:

  * **Drizzle ORM** with PostgreSQL.
  * Study all schemas in `src/lib/db`.
  * **Do not create or modify DB schemas**.
  * Update `src/lib/actions/product.ts`:

    * Refine `getProduct(productId)` to fetch product + variants + images + metadata.
    * Create new server actions:

      * `getProductReviews(productId)` → returns approved reviews.
      * `getRecommendedProducts(productId)` → returns related products.

* **Rendering**:

  * The main PDP is server-rendered.
  * Reviews + Also Like are server-rendered too, but loaded inside `Suspense` so they never block main PDP rendering.

## ✅ Tasks

1. **Refine `getProduct`**

   * Input: `productId`.
   * Return:

     * Title, subtitle, description, price, compare price.
     * Variants (color, size, stock, price).
     * Images grouped by variant.
     * Category, brand, gender.
   * Use Drizzle relations (no N+1 queries).
   * Return `null` if product doesn’t exist.

2. **Implement `getProductReviews(productId)`**

   * Returns array of:

     ```ts
     type Review = {
       id: string;
       author: string;
       rating: number;
       title?: string;
       content: string;
       createdAt: string;
     }
     ```
   * Only approved reviews.
   * Sorted by newest first.
   * Dummy if no DB data exists.

3. **Implement `getRecommendedProducts(productId)`**

   * Fetch products in the same category/brand/gender.
   * Limit: 4–6.
   * Must return: ID, title, price, main image.
   * Gracefully skip products with invalid/missing images.

4. **Page Implementation (`page.tsx`)**

   * Server component.
   * Read `{ params: { id } }`.
   * Call `getProduct(id)`.

     * If `null`, render a styled custom Not Found block.
   * Render:

     * **Gallery** (client component).
     * **Variant picker** (client, UI-only).
     * **Meta info** (server).
   * Wrap Reviews + Also Like in `Suspense` with skeleton fallback.

5. **Reviews Component**

   * Server-rendered.
   * Display stars (Lucide `Star`).
   * Collapsible text for longer reviews.
   * Show first 10 reviews.

6. **Also Like Component**

   * Server-rendered.
   * Grid of existing `Card.tsx`.
   * Cards link to `/products/[id]`.
   * Hide if list empty or invalid.

7. **Navigation**

   * Clicking product cards across the app leads to `/products/[id]`.

8. **Responsiveness & Design**

   * Desktop: pixel-perfect to screenshot.
   * Mobile/Tablet: strictly follow provided layouts.
   * Product gallery on mobile:

     * Main image at top.
     * Thumbnails scrollable below.
     * Rest of content flows in single column.

9. **Accessibility**

   * Semantic HTML.
   * Alt text for images.
   * Keyboard support for gallery thumbnails and swatches.

## 📦 Output Requirements

* Clean and well-typed server actions:

  * `getProduct(productId)`
  * `getProductReviews(productId)`
  * `getRecommendedProducts(productId)`

* `page.tsx` server-rendered PDP that:

  * Fetches product.
  * Shows reviews + recommendations via `Suspense`.
  * Handles missing products gracefully.
  * Renders gallery only if valid images exist.

* Pixel-perfect UI at all breakpoints.

* Consistent theme usage (`globals.css`).

* Clear separation of **server vs client** components.

* Super clean, easy-to-read code with proper naming.

## 📝 Notes

* Do not touch DB schemas.
* Use Drizzle relations properly — no hacks.
* All server actions must have **explicit TypeScript return types**.
* Use `next/image` with `sizes` + defined width/height to prevent layout shifts.
* Keep logic modular and reusable (avoid bloated components).
* The PDP should be **future-proof** so cart/favorite logic can be added later with minimal refactor.
* ==================================================================================
* Cart Functionality Prompt
* You are a senior full-stack engineer assigned to build a modern web application from scratch.

## 💼 Objective

Implement a fully functional and responsive **Cart System** that integrates with both authenticated users and guest sessions, keeping cart state consistent across all pages and sessions.

## ⚙️ Structure

* **Framework**: Next.js 14 (App Router)
* **Database ORM**: Drizzle ORM with PostgreSQL (schemas already exist, no modifications needed at all)
* **State Management**: Zustand (for cart global state)
* **Styling**: Tailwind CSS (strictly follow theme guidelines from `globals.css`)
* **Icons**: Lucide Icons
* **Auth & Sessions**: Guest + User session handling (already implemented in `src/lib/auth/actions.ts`)
* File folders

	/src
	├── app/
	│   ├── (root)/
	│   │   ├── cart/
	│   │   │   └── page.tsx              ← cart page (SSR + client integration)
	├── components/                       ← implement cart related components inside this folder
	├── lib/
	│   ├── auth/
	│   │   └── actions.ts                ← guest session + user session handling. It's already there. 
	│   ├── actions/
	│   │   └── cart.ts                   ← cart server actions (CRUD)
	│   └── utils/
	│       └── query.ts                  ← helpers for parsing/stringifying URL filters
	├── store/
	│   └── cart.store.ts                  ← Zustand cart global state
	


## ✅ Tasks

1. **Cart Page UI**

   * Build a cart page **strictly following the attached design screenshot**.
   * Ensure responsiveness across desktop, tablet, and mobile (main image/galleries handled as per responsive rules).
   * Follow consistent theme and component usage from existing codebase.

2. **Global State (Zustand)**

   * Create a cart global state in `src/store/cart.store.ts`.
   * Integrate cart state in navbar (cart indicator) and cart page.
   * Ensure updates are reflected instantly across pages when items are added/removed/updated.

3. **Server Actions (`src/lib/actions/cart.ts`)**

   * Implement the following **industry-standard named** server actions:

     * `getCart` – fetch all cart items for user/guest
     * `addCartItem` – add a product variant to cart
     * `updateCartItem` – update quantity/variant in cart
     * `removeCartItem` – remove item from cart
     * `clearCart` – empty cart (optional but recommended)
   * Ensure correct integration between global state and these server actions.

4. **Guest Session Handling**

   * If no user exists, create/maintain a guest session in cart flow.
   * If a user signs up/logs in after creating a guest session → merge guest session cart into user cart.
   * If user already logged in, proceed normally.

5. **Checkout Flow**

   * If a guest user clicks **Checkout**, redirect them to `/auth` page for login/signup.
   * After successful login/signup, merge guest session cart into user cart and continue.
   * If already logged in → proceed to checkout without interruption.

## 📌 Output Requirements

* Fully functional cart page (UI + global state + server actions).
* Cart state is **always consistent** across all pages and sessions.
* Works seamlessly for both guest and authenticated users.
* Follows **file/folder structure** and **theme guidelines** strictly.
* Code should be production-ready, clean, and maintainable.

## 📝 Notes

* Do not modify any existing DB schema.
* Ensure server action names follow **best practices** (`getCart`, `addCartItem`, `updateCartItem`, `removeCartItem`).
* Must use Lucide icons where necessary (cart icon, delete icon, etc.).
* Keep UI responsive across desktop, tablet, and mobile, following attached screenshots.
====================================================================
Stripe Integration Prompt
You are a senior full-stack engineer assigned to integrate **Stripe Checkout** into the e-commerce platform.

## Objective

Implement a seamless **Stripe Checkout integration** that supports both **guest sessions** and **authenticated users**. The flow must handle cart persistence, create Stripe checkout sessions securely on the server, and redirect users to Stripe’s hosted checkout page. After successful payment, orders should be stored in the database and linked to the correct user (or merged guest session).

## Structure

* Use **Next.js 14 App Router**, **TypeScript**, **Drizzle ORM**, and **PostgreSQL**.
* Strictly follow theme guidelines 
* Follow the file/folder structure:
	```
	/src
	├── app/
	│   ├── (root)/
	│   │   ├── cart/
	│   │   │   └── page.tsx              ← cart page with checkout button
	│   │   ├── checkout/
	│   │   │   └── success/page.tsx      ← order success page
	│   │   api/
	│   │   ├── stripe/
	│   │        └── route.ts             ← webhook handler for Stripe events
	│   └── layout.tsx
	│
	├── components/
	│   ├── CartSummary.tsx               ← cart total + checkout button
	│   └── OrderSuccess.tsx              ← success UI after checkout
	│
	├── lib/
	│   ├── stripe/
	│   │   └── client.ts                 ← stripe client instance
	│   ├── actions/
	│   │   ├── checkout.ts               ← server action: createStripeCheckoutSession
	│   │   └── orders.ts                 ← server actions: createOrder, getOrder
	│   └── utils/
	│       └── mergeSessions.ts          ← helper to merge guest + user sessions
	```

## Tasks

### 1. **Setup Stripe**

* Add `stripe` NPM package.
* Create `/src/lib/stripe/client.ts` exporting initialized Stripe instance with `process.env.STRIPE_SECRET_KEY`.
* Store publishable key in `NEXT_PUBLIC_STRIPE_PUBLISHABLE_KEY`.

### 2. **Cart Checkout Button**

* Add a **Checkout button** in `CartSummary.tsx`.
* On click, call **`createStripeCheckoutSession`** (server action).
* Redirect user to Stripe Checkout URL returned from the server.

### 3. **Server Actions**

* **`createStripeCheckoutSession(cartId: string)`**

  * Fetch cart items from DB (merge guest + user if needed).
  * Create a Stripe Checkout session with line items.
  * Return checkout URL.

* **`createOrder(stripeSessionId: string, userId?: string)`**

  * On successful payment (via webhook), insert order in DB with associated cart + user.

* **`getOrder(orderId: string)`**

  * Retrieve order details for success page.

### 4. **Webhook Handling**

* Implement `/app/api/stripe/route.ts`.
* Listen to Stripe events:

  * `checkout.session.completed`: call `createOrder`.
  * `payment_intent.payment_failed`: log failure.
* Ensure webhook is secured using Stripe signature verification.

### 5. **Success Page**

* Create `/checkout/success/page.tsx`.
* Fetch order by session/orderId.
* Show `OrderSuccess.tsx` with purchased items + total amount.

## Output Requirements

* Fully working **Stripe Checkout integration** with server actions.
* Checkout flow must work for **guest sessions** and **authenticated users**.
* Orders must persist in DB with proper user linkage.
* Webhooks must be verified and idempotent.
* UI should use **Lucide icons**, **Tailwind**, and be **responsive**.
* Code must follow **TypeScript strict mode** and Next.js **App Router conventions**.

## Notes

* Place **all server actions inside `/src/lib/actions`**.
* Use strict naming: `createStripeCheckoutSession`, `createOrder`, `getOrder`.
* Cart session merging logic is already in `src/lib/auth/actions.ts`. Use it before creating Stripe session.
* Ensure empty carts cannot initiate checkout.
* Store all monetary values as **integers in smallest currency unit** (e.g., cents).






