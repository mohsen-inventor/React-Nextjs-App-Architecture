# React / Next.js App Architecture

```bash
# App Root Level
├── _sass (global styles)
    ├── config
        ├── base.scss (vars, colors, etc)
        ├── fonts.scss
        ├── iconFont.scss
        ├── breakpoints.scss
        ├── ltr.scss (vars, mixins only for Multilingual layout)
        ├── rtl.scss (vars, mixins only for Multilingual layout)
        ├── index.scss (export all config files)
    ├── libs (3rd party libs customizations, ex. swiper)
    ├── helpers (helper mixins)
    ├── shared.scss (imported in each component)
    ├── global.scss (imported once in app root)
├── _components (all app components classified by category/feature)
    ├── _layout
            ├── _mobile (custom for ios/android if needed)
            ├── PageLayout (main layout includes header, footer)
                ├── PageLayout.tsx
                ├── PageLayout.module.scss
            ├── AuthLayout
            ├── AdminLayout
            ├── Header
            ├── Footer
            ├── SidePanel
            ├── SideMenu
            ├── index.ts (export all components)
    ├── _hoc (higher order components if needed)
        ├── withAuth.hoc.tsx
        ├── withLoading.hoc.tsx
        ├── withError.hoc.tsx
        ├── index.ts (export all components)
    ├── _ui (atomic stateless ui components)
        ├── form
            ├── _mobile (custom ios/android components if needed)
            ├── Button
                ├── Button.tsx
                ├── Button.module.scss
            ├── Input (can be generic to support many types)
            ├── Select
            ├── Checkbox 
            ├── Radio
            ├── Switch
            ├── index.ts (export all components)
        ├── Media
            ├── Image
            ├── Video
            ├── Audio
            ├── index.ts (export all components)
        ├── Navigation
            ├── Breadcrumb
            ├── Pagination
            ├── Tabs
            ├── Accordion
            ├── index.ts (export all components)
    ├── home (feature module, unique home page components only)
    ├── userProfile (as feature module)
        ├── userSettings (as feature component)
            ├── AccountSettings (as child component)
                ├── AccountSettings.tsx
                ├── AccountSettings.module.scss
            ├── PreferencesSettings (as child component)
                ├── PreferencesSettings.tsx
                ├── PreferencesSettings.module.scss
            ├── UserSettings.tsx
            ├── UserSettings.module.scss
    ├── authentication (as feature module)
        ├── AuthMain (as feature component)
            ├── SignIn
                ├── SignIn.tsx
                ├── SignIn.module.scss
            ├── SignUp
                ├── SignUp.tsx
                ├── SignUp.module.scss
            ├── ForgotPassword
                ├── ForgotPassword.tsx
                ├── ForgotPassword.module.scss
            ├── ResetPassword
                ├── ResetPassword.tsx
                ├── ResetPassword.module.scss
            ├── AuthMain.tsx
            ├── AuthMain.module.scss
├── pages (very clean, minimum logic, get data, stack components)
    ├── api (API routes)
    ├── about.tsx 
    ├── contact.tsx
    ├── index.tsx (Home page)
├── public (Public files)
    ├── images (Public images)
    ├── icons (Public icons)
    ├── fonts (Public text/icon fonts)
    ├── favicon.ico
├── graphql (GraphQL api)
    ├── fragments
    ├── types
    ├── posts (queries, mutations)
    ├── users (queries, mutations)
├── hooks
    ├── data (fetch data > update store > side effect > return data)
        ├── posts
            ├── usePosts.data.ts ('use' hook prefix, '.data.ts' as suffix)
            ├── useUpdatePost.data.ts
            ├── index.ts (export all hooks)
        ├── users
            ├── useUsers.data.ts
            ├── useUpdateUser.data.ts
            ├── index.ts (export all hooks)
    ├── ui (ui/animation hooks)
        ├── useScrollPosition.ui.ts
        ├── index.ts (export all hooks)
├── logic (business logic)
├── common (common constants, enums, etc)
├── types (typescript definitions)  
├── helpers (utility functions)
    ├── http (custom axios instance if needed)
        ├── axiosUser.ts
    ├── form (form helpers)
    ├── date (date formatters)
    ├── storage (storage helpers)
├── providers
    ├── apolloClient.ts (if using GraphQL)
├── context
├── store (global app state using redux toolkit)
    ├── auth
        ├── authSlice.ts (reducers, actions, side effects)
        ├── selectors.ts (select from auth state)
    ├── store.ts
├── config (app config)
    ├── authConfig.ts
├── .next (Next.js build output)
├── .storybook (Storybook config)
├── .vscode (VSCode config)
├── .gitignore (Git ignore config)
├── .prettierrc (Prettier config)
├── .eslintrc (ESLint config)
├── .babelrc (Babel config)
├── .env (Environment variables)
├── .env.development (Environment variables for development)
├── .env.production (Environment variables for production)
├── .env.staging (Environment variables for staging)
├── .env.test (Environment variables for test)
├── .env.local (Environment variables for local)