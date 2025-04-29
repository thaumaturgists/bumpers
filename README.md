### bumpers

# Ruby on Rails with TypeScript and React

This project is a simple Ruby on Rails application integrated with TypeScript and React. It demonstrates how to set up a Rails API with a TypeScript front-end using Webpacker.

## Getting Started

### Prerequisites

- Ruby (version 2.7 or higher)
- Rails (version 6 or higher)
- Node.js (version 12 or higher)
- Yarn (for managing JavaScript packages)

### Installation

1. **Create a new Rails app**:
   ```bash
   rails new bumpers --webpack=react
   cd bumpers
   ```

2. **Install TypeScript**:
   ```bash
   rails webpacker:install:typescript
   ```

3. **Create a TypeScript React component**:
   Create a file named `HelloWorld.tsx` in `app/javascript/components/`:
   ```tsx
   // app/javascript/components/HelloWorld.tsx
   import React from 'react';

   const HelloWorld: React.FC = () => {
     return <h1>Hello, TypeScript with Rails!</h1>;
   };

   export default HelloWorld;
   ```

4. **Render the component in a Rails view**:
   Create a file named `index.html.erb` in `app/views/home/`:
   ```erb
   <!-- app/views/home/index.html.erb -->
   <div id="hello-world"></div>
   <%= javascript_pack_tag 'application' %>
   ```

5. **Mount the component**:
   Update `application.tsx` in `app/javascript/packs/`:
   ```tsx
   // app/javascript/packs/application.tsx
   import React from 'react';
   import ReactDOM from 'react-dom';
   import HelloWorld from '../components/HelloWorld';

   document.addEventListener('DOMContentLoaded', () => {
     ReactDOM.render(<HelloWorld />, document.getElementById('hello-world'));
   });
   ```

### Running the Application

1. **Start the Rails server**:
   ```bash
   rails server
   ```

2. **Visit the application**:
   Open your browser and go to `http://localhost:3000/home/index`.

### Conclusion

Using TypeScript with Ruby on Rails enhances your development experience by providing type safety and modern JavaScript capabilities. This setup is a great starting point for building robust and maintainable applications.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
```

### Project Structure

Here's a simple project structure based on the provided information:

```
bumpers/
├── app/
│   ├── assets/
│   ├── controllers/
│   ├── javascript/
│   │   ├── components/
│   │   │   └── HelloWorld.tsx
│   │   └── packs/
│   │       └── application.tsx
│   ├── views/
│   │   └── home/
│   │       └── index.html.erb
│   └── models/
├── config/
├── db/
├── Gemfile
├── package.json
├── tsconfig.json
└── ...
```

### Notes

- Make sure to install the necessary gems and dependencies as specified in the `Gemfile` and `package.json`.
- You can customize the components and views as needed for your application.
- This setup assumes you have a basic understanding of Ruby on Rails and React.
