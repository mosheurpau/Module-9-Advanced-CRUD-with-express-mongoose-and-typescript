# Project Overview

This project provides an overview of the **Mongoose** library and its integration with **MongoDB** databases in a TypeScript environment. The setup includes tools for formatting and error detection, alongside a focus on software design patterns for improved code structure and maintainability.

## Features

1. **Mongoose Integration**:
   - Setting up Mongoose for MongoDB.
   - Designing schemas and models.
2. **Express.js Setup**:
   - Middleware configuration.
   - Routing.
3. **TypeScript Integration**:
   - Leveraging TypeScript for type safety.
   - Creating and using interfaces.
4. **Project Enhancements**:
   - Using `prettier-ts-node-dev` for automatic code formatting.
   - Using ESLint to detect and address errors.
5. **Design Patterns**:
   - Comparing **MVC** and modular design patterns.
   - Applying the most suitable pattern for the application.
6. **Validation Module**:
   - Introduction to validation.
   - Utilizing the Joi package for schema validation.
   - Implementing custom validation techniques.
   - Exploring instance method validation.
   - Integrating Zod for advanced validation.

## Getting Started

### Prerequisites

Ensure you have the following installed:
- Node.js
- npm or yarn
- MongoDB

### Installation

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd <project-folder>
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Set up environment variables:
   - Create a `.env` file in the root directory.
   - Define the necessary variables, e.g., `MONGO_URI`.

4. Start the development server:
   ```bash
   npm run dev
   ```

### Additional Scripts

- `npm run format`: Format the code using Prettier.
- `npm run lint`: Run ESLint to identify and fix issues.

## Project Structure

```
├── src
│   ├── controllers
│   │   └── studentController.ts
│   ├── models
│   │   └── studentModel.ts
│   ├── routes
│   │   └── studentRoutes.ts
│   ├── services
│   │   └── studentService.ts
│   ├── interfaces
│   │   └── studentInterface.ts
│   ├── validations
│   │   ├── joiValidation.ts
│   │   └── zodValidation.ts
│   └── app.ts
├── .env
├── .eslintrc.js
├── .prettierrc
├── tsconfig.json
└── package.json
```

## Concepts Covered

### Mongoose Setup
- Defining schemas and models.
- Connecting to a MongoDB database.

### Software Design Patterns
- Implementing the MVC pattern.
- Exploring modular alternatives.

### TypeScript
- Creating interfaces for strong typing.

### Validation
- Introduction to validation principles.
- Practical validation using Joi.
- Advanced validation techniques using Zod.
- Instance method validation.

### Enhancements
- Using `prettier-ts-node-dev` for consistent formatting.
- Detecting and resolving errors with ESLint.

## Application Example

### Student Schema
Define a schema for student data:
```typescript
import { Schema, model } from 'mongoose';

const studentSchema = new Schema({
    name: { type: String, required: true },
    age: { type: Number, required: true },
    enrolled: { type: Boolean, default: false },
});

export const Student = model('Student', studentSchema);
```

### Routes Example
Define a route to handle student requests:
```typescript
import { Router } from 'express';
import { getAllStudents } from '../controllers/studentController';

const router = Router();

router.get('/students', getAllStudents);

export default router;
```

### Validation Example
Using Joi for schema validation:
```typescript
import Joi from 'joi';

const studentValidationSchema = Joi.object({
    name: Joi.string().required(),
    age: Joi.number().integer().required(),
    enrolled: Joi.boolean().optional(),
});

export const validateStudent = (data: any) => {
    return studentValidationSchema.validate(data);
};
```

## Refactoring and Future Work
- Enhance schema design by incorporating relationships and validation.
- Explore additional design patterns and refactor the application accordingly.

---

**Author**: Mosheur Rahman
