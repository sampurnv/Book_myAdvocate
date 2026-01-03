# Migration Notes: Frontend/Backend Split

## Overview
This repository has been reorganized to better separate frontend and backend code.

## Directory Changes

| Old Structure | New Structure |
|--------------|---------------|
| `client/`    | `frontend/`   |
| `server/`    | `backend/`    |

## What Changed

### 1. Directory Renaming
- All files from `client/` have been moved to `frontend/`
- All files from `server/` have been moved to `backend/`
- Git history has been preserved through rename detection

### 2. Documentation Updates
- `README.md` - Updated all path references
- `SETUP.md` - Updated installation instructions
- `frontend/README.md` - Updated internal references
- `vercel.json` - Updated build configuration

### 3. No Breaking Changes
- All `package.json` files remain unchanged
- All dependencies remain the same
- All scripts continue to work as before

## Migration Guide

### For Existing Clones

If you have an existing clone of this repository:

```bash
# Pull the latest changes
git fetch origin
git checkout split/frontend-backend
git pull origin split/frontend-backend

# The old client/ and server/ directories will be automatically 
# renamed to frontend/ and backend/
```

### For New Development

```bash
# Backend development
cd backend
npm install
npm run dev

# Frontend development (in a new terminal)
cd frontend
npm install
npm start
```

### For CI/CD Pipelines

Update any scripts or configurations that reference:
- `client/` → `frontend/`
- `server/` → `backend/`

### For Documentation

All documentation has been updated to reflect the new structure. No action required.

## Why This Change?

1. **Clarity**: "frontend" and "backend" are more universally understood terms
2. **Convention**: Many modern monorepos use this naming convention
3. **Scalability**: Clearer separation for future microservices architecture
4. **Onboarding**: Easier for new developers to understand the project structure

## Questions?

If you have any questions about this migration, please open an issue in the repository.
