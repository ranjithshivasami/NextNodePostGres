
<details>
<summary>
<strong>Next.js Interview Questions
</strong></summary>

## Table of Contents
- [Table of Contents](#table-of-contents)
  - [What is Next.js, and why is it used?](#what-is-nextjs-and-why-is-it-used)
  - [What are the differences between Next.js and React?](#what-are-the-differences-between-nextjs-and-react)
  - [Explain the file-based routing in Next.js.](#explain-the-file-based-routing-in-nextjs)
  - [What are the rendering methods available in Next.js?](#what-are-the-rendering-methods-available-in-nextjs)
  - [How do you create dynamic routes in Next.js?](#how-do-you-create-dynamic-routes-in-nextjs)
  - [What is the purpose of the getStaticProps function?](#what-is-the-purpose-of-the-getstaticprops-function)
  - [How does getServerSideProps work?](#how-does-getserversideprops-work)
  
### What is Next.js, and why is it used?
Next.js is a React-based framework for building server-side rendered (SSR) and static web applications.
**Key Features:**
- Automatic routing
- Server-side rendering (SSR)
- Static site generation (SSG)
- API routes
- Optimized image loading

---
###  What are the differences between Next.js and React?

  | Aspect      | React                            | Next.js                                |
  |-------------|----------------------------------|----------------------------------------|
  | Rendering   | CSR by default                   | CSR, SSR, SSG, ISR supported           |
  | Routing     | Custom setup with React-Router   | Built-in file-based routing            |
  | Performance | Dependent on manual tuning       | Automatic performance optimization     |

---

### Explain the file-based routing in Next.js.
Next.js uses the pages/ directory to define routes.
**Example:**

- pages/index.js → /
- pages/about.js → /about
- Dynamic routes: pages/blog/[id].js → /blog/:id
---

### What are the rendering methods available in Next.js?
- Static Site Generation (SSG): Pre-generates HTML at build time.
- Server-Side Rendering (SSR): Generates HTML at runtime on each request.
- Client-Side Rendering (CSR): Relies on React for rendering after page load.
- Incremental Static Regeneration (ISR): Updates static pages without full rebuilds.

---

### How do you create dynamic routes in Next.js?
Use square brackets in the pages/ folder.
**Example:**

- File: pages/product/[id].js
- Access: /product/123

```javascript
import { useRouter } from 'next/router';

const ProductPage = () => {
  const router = useRouter();
  const { id } = router.query;
  return <div>Product ID: {id}</div>;
};
export default ProductPage;

```
---


### What is the purpose of the getStaticProps function?

getStaticProps generates static content at build time.
Example:

```javascript

export async function getStaticProps() {
  const data = await fetch('https://api.example.com');
  return { props: { data } };
}

```
---


### How does getServerSideProps work?
getServerSideProps runs on the server for every request to pre-render the page.

```javascript

export async function getServerSideProps() {
  const data = await fetch('https://api.example.com');
  return { props: { data } };
}
```

 ---
 </details>
