# Basic Routes in Next.js

This section explains how basic routing works in the Next.js App Router.

The examples in this folder are focused on route structure only. They are learning examples, not complete standalone apps.

## Core Idea

In the App Router:

- Every folder inside `app` becomes part of the URL.
- A `page.tsx` file creates a page for that URL.
- A `layout.tsx` file wraps all pages inside that section.

## Quick Examples

```txt
app/page.tsx            -> /
app/about/page.tsx      -> /about
app/login/page.tsx      -> /login
app/blog/1/page.tsx     -> /blog/1
app/blog/2/page.tsx     -> /blog/2
```

## 1. Live Coding

Path: [`1. Live Coding`](./1.%20Live%20Coding)

This is the most basic example in this section.

### Route Map

- `app/page.tsx` -> `/`
- `app/about/page.tsx` -> `/about`
- `app/login/page.tsx` -> `/login`

### What It Teaches

- How to create a home page
- How to create simple static pages
- How folder names become route names

## 2. Blogs Project

Path: [`2. Blogs Project`](./2.%20Blogs%20Project)

This example shows multiple static pages for a small blog.

### Route Map

- `app/page.tsx` -> `/`
- `app/about/page.tsx` -> `/about`
- `app/blog/1/page.tsx` -> `/blog/1`
- `app/blog/2/page.tsx` -> `/blog/2`

### What It Teaches

- How to organize routes in nested folders
- How `/blog/1` and `/blog/2` are created from folder structure
- How to link from the home page to individual blog pages

### Important Note

These blog routes are static routes.

That means:

- `/blog/1` is created by the folder `blog/1`
- `/blog/2` is created by the folder `blog/2`

This is different from dynamic routing like `app/blog/[id]/page.tsx`.

## 3. Challenge

Path: [`3. Challenge`](./3.%20Challenge)

This folder contains a small practice task and its solution.

### Instructions

Goal:

- Create an `about` page
- Create a `contact` page
- Check that both routes work correctly

### Solution Route Map

- `app/page.tsx` -> `/`
- `app/about/page.tsx` -> `/about`
- `app/contact/page.tsx` -> `/contact`

## Role of `layout.tsx`

Some examples include `layout.tsx`.

`layout.tsx` is used to wrap all pages in that app section. It usually contains:

- shared HTML structure
- fonts
- metadata
- global wrappers

`layout.tsx` does not create a new route by itself.

## Simple Rule to Remember

If you want a route like this:

```txt
/services/web
```

The folder structure will usually look like this:

```txt
app/
  services/
    web/
      page.tsx
```

## Common Beginner Mistakes

- Creating a folder but forgetting to add `page.tsx`
- Expecting `layout.tsx` to behave like a page
- Mixing static routes with dynamic routes without understanding the difference
- Using the wrong folder name and getting the wrong URL

## Summary

Basic routing in Next.js App Router is folder-based.

- `page.tsx` creates the page
- folder names create the URL
- nested folders create nested routes
- `layout.tsx` wraps pages, but does not create a route

If you understand this section, you are ready for nested routes and dynamic routes next.
