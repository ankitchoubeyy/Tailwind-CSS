![Tailwind CSS](./TailwindCSS/public/tailwindLogo.jpg);

**Tailwind CSS** is an open source CSS framework. 
- The main feature of this library is that, unlike other CSS frameworks like Bootstrap, it does not provide a series of predefined classes for elements such as buttons or tables.

### Why Tailwind CSS?

- The faster UI building process
- It is a utility-first CSS framework which means we can use utility classes to build custom designs without writing CSS as in the traditional approach.

### Advantages
- No more silly names for CSS classes and Id.
- Minimum lines of Code in CSS file.
- We can customize the designs to make the components.
- Makes the website responsive.
- Makes the changes in the desired manner. 
- CSS is global in nature and if make changes in the file the property is changed in all the HTML files linked to it. But with the help of Tailwind CSS, we can use utility classes and make local changes.

**Example:** 
```
<h1 className='text-red-400 text-center text-3xl font-extrabold py-2'>Jai Shree Ram!</h1>
```

### Custom CSS in Tailwind
1. **Using Arbitary values.**
```
<div class="top-[117px]">
  <!-- ... -->
</div>
```
2. **Customizing your theme**
If you want to change things like your color palette, spacing scale, typography scale, or breakpoints, add your customizations to the theme section of your tailwind.config.js file:
```
/** @type {import('tailwindcss').Config} */
module.exports = {
  theme: {
    screens: {
      sm: '480px',
      md: '768px',
      lg: '976px',
      xl: '1440px',
    },
    colors: {
      'blue': '#1fb6ff',
      'pink': '#ff49db',
      'orange': '#ff7849',
      'green': '#13ce66',
      'gray-dark': '#273444',
      'gray': '#8492a6',
      'gray-light': '#d3dce6',
    },
    fontFamily: {
      sans: ['Graphik', 'sans-serif'],
      serif: ['Merriweather', 'serif'],
    },
    extend: {
      spacing: {
        '128': '32rem',
        '144': '36rem',
      },
      borderRadius: {
        '4xl': '2rem',
      }
    }
  }
}
```

> **Note:** Tailwind CSS uses **JIT** (Just in Time) copmiler to run an utilites classes.

### Resusing Styles 
To resuse same style again and again you can use different Resusing styles methods which are given below:-

1. Use of Multicursor Feature.
2. Use of loop to render the componnts.
3. Extracting classes with @apply
```
<!-- Before extracting a custom class -->
<button class="py-2 px-4 bg-blue-500 text-white font-semibold rounded-lg shadow-md hover:bg-blue-700 focus:outline-none focus:ring-2 focus:ring-blue-400 focus:ring-opacity-75">
  Save changes
</button>

<!-- After extracting a custom class -->
<button class="btn-primary">
  Save changes
</button>
```
```
@tailwind base;
@tailwind components;
@tailwind utilities;

@layer components {
  .btn-primary {
    @apply py-2 px-4 bg-blue-500 text-white font-semibold rounded-lg shadow-md hover:bg-blue-700 focus:outline-none focus:ring-2 focus:ring-blue-400 focus:ring-opacity-75;
  }
}
```
**Disclaimer**
- Whatever you do, don’t use @apply just to make things look “cleaner”. Yes, HTML templates littered with Tailwind classes are kind of ugly. Making changes in a project that has tons of custom CSS is worse.

- If you start using @apply for everything, you are basically just writing CSS again and throwing away all of the workflow and maintainability advantages Tailwind gives you.
