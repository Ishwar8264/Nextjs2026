# Nested Routes in Next.js

This section explains how nested routes work in the Next.js App Router.

Nested routing means creating folders inside folders inside the `app` directory. Each folder adds one more part to the URL.

## Core Idea

In the App Router:

- every folder becomes part of the route
- every `page.tsx` creates a page
- nested folders create nested URLs

## Simple Rule

If you want this route:

```txt
/dashboard/settings/profile
```

Your folder structure will usually look like this:

```txt
app/
  dashboard/
    settings/
      profile/
        page.tsx
```

## Quick Examples

```txt
app/users/page.tsx                    -> /users
app/users/about/page.tsx              -> /users/about
app/users/about/projects/page.tsx     -> /users/about/projects
app/dashboard/page.tsx                -> /dashboard
app/dashboard/tasks/page.tsx          -> /dashboard/tasks
app/dashboard/settings/profile/page.tsx -> /dashboard/settings/profile
```

## 1. Live Coding

Path: [`1. Live Coding`](./1.%20Live%20Coding)

This example shows the basic idea of nested routes.

### Route Map

- `app/page.tsx` -> `/`
- `app/users/page.tsx` -> `/users`
- `app/users/about/page.tsx` -> `/users/about`
- `app/users/about/projects/page.tsx` -> `/users/about/projects`

### What It Teaches

- how one folder creates one part of the URL
- how deeper folders create deeper routes
- how nested pages are organized in a clean folder structure

## 2. Dashboard Project

Path: [`2. Dashboard Project`](./2.%20Dashboard%20Project)

This example shows nested routes in a more realistic app structure.

### Main Route Map

- `app/page.tsx` -> `/`
- `app/dashboard/page.tsx` -> `/dashboard`
- `app/dashboard/analytics/page.tsx` -> `/dashboard/analytics`
- `app/dashboard/tasks/page.tsx` -> `/dashboard/tasks`
- `app/dashboard/users/page.tsx` -> `/dashboard/users`
- `app/dashboard/settings/page.tsx` -> `/dashboard/settings`

### Deeper Nested Routes

- `app/dashboard/users/users-list/page.tsx` -> `/dashboard/users/users-list`
- `app/dashboard/users/users-details/page.tsx` -> `/dashboard/users/users-details`
- `app/dashboard/settings/account/page.tsx` -> `/dashboard/settings/account`
- `app/dashboard/settings/profile/page.tsx` -> `/dashboard/settings/profile`
- `app/dashboard/settings/notifications/page.tsx` -> `/dashboard/settings/notifications`

### What It Teaches

- how to build sections inside a dashboard
- how child routes can live inside parent folders
- how routes like `/dashboard/users/users-list` come directly from folder nesting

## 3. Challenge

Path: [`3. Challenge`](./3.%20Challenge)

This folder contains a small nested routing exercise and its solution.

### Challenge Goal

Create a `products` route and inside it create two more nested routes:

- `/products/allproducts`
- `/products/specificproduct`

### Solution Route Map

- `app/page.tsx` -> `/`
- `app/products/page.tsx` -> `/products`
- `app/products/allproducts/page.tsx` -> `/products/allproducts`
- `app/products/specificproduct/page.tsx` -> `/products/specificproduct`

## Route Tree View

This is how nested routes grow step by step:

```txt
app/
  dashboard/
    page.tsx
    analytics/
      page.tsx
    tasks/
      page.tsx
    users/
      page.tsx
      users-list/
        page.tsx
      users-details/
        page.tsx
    settings/
      page.tsx
      account/
        page.tsx
      profile/
        page.tsx
      notifications/
        page.tsx
```

## Nested Routes vs Basic Routes

Basic route example:

```txt
app/about/page.tsx -> /about
```

Nested route example:

```txt
app/users/about/page.tsx -> /users/about
```

The difference is simple:

- basic routes usually have one folder level
- nested routes have multiple folder levels

## Role of `layout.tsx`

Some examples include `layout.tsx`.

`layout.tsx` wraps pages, but it does not create a route by itself.

So:

- `page.tsx` creates the route
- `layout.tsx` shares structure across pages

## Common Beginner Mistakes

- forgetting to create `page.tsx` inside a nested folder
- expecting a folder alone to create a page
- mixing up the folder name and the final URL
- thinking nested routes need a separate `layout.tsx` every time

## Summary

Nested routing in Next.js is folder-based.

- one folder adds one part to the URL
- nested folders create nested URLs
- `page.tsx` creates the actual page
- deeper structure gives deeper routes like `/dashboard/settings/profile`

If you understand this section, you can move next to dynamic routes and more advanced App Router patterns.
