# Pull Request: Split Frontend and Backend

## Summary
This PR reorganizes the BookMyAdvocate repository by renaming `client/` to `frontend/` and `server/` to `backend/` for better code organization and clarity.

## Branch
- **Source Branch**: `split/frontend-backend`
- **Target Branch**: `main` (or default branch)

## Changes

### Directory Structure
```diff
- client/     → frontend/
- server/     → backend/
  database/   (unchanged)
```

### Files Modified
1. **README.md**
   - Updated all references from `client/` to `frontend/`
   - Updated all references from `server/` to `backend/`
   - Updated installation instructions
   - Updated project structure documentation

2. **SETUP.md**
   - Updated setup instructions with new directory names
   - Updated troubleshooting paths

3. **vercel.json**
   - Updated build source path from `client/package.json` to `frontend/package.json`

4. **frontend/README.md**
   - Updated internal path references
   - Updated project structure diagram

5. **MIGRATION_NOTES.md** (New)
   - Comprehensive migration guide for developers
   - Explains directory changes
   - Provides migration instructions

### Git History
All files were detected as **renames** by Git, preserving the complete history.

### No Breaking Changes
- All `package.json` files remain unchanged
- All dependencies are identical
- All npm scripts work as before
- No code logic changes

## Testing

### Verified Structure
```
BookMyAdvocate/
├── frontend/
│   ├── src/
│   ├── public/
│   └── package.json
├── backend/
│   ├── config/
│   ├── middleware/
│   ├── routes/
│   └── package.json
└── database/
```

### Scripts Still Work
- ✅ Backend: `cd backend && npm install && npm start`
- ✅ Frontend: `cd frontend && npm install && npm start`
- ✅ Database: `cd backend && npm run init-db`

## Benefits

1. **Clearer Naming**: "frontend" and "backend" are universally understood
2. **Better Organization**: Follows modern monorepo conventions
3. **Easier Onboarding**: New developers can quickly understand the structure
4. **Future-Proof**: Better foundation for potential microservices architecture

## Migration for Users

For existing clones:
```bash
git fetch origin
git checkout split/frontend-backend
git pull origin split/frontend-backend
```

The directories will be automatically renamed with full history preserved.

## Checklist
- [x] Created `frontend/` directory
- [x] Created `backend/` directory
- [x] Moved all client files to frontend
- [x] Moved all server files to backend
- [x] Updated README.md
- [x] Updated SETUP.md
- [x] Updated vercel.json
- [x] Updated frontend/README.md
- [x] Created MIGRATION_NOTES.md
- [x] Verified all scripts work
- [x] Preserved git history

## Review Notes
Please review the documentation updates to ensure all references have been properly updated. The actual code remains unchanged - this is purely a structural reorganization.
