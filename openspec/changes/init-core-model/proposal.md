# Change: Initialize Core Data Model

## Why
We need to establish the foundational entities for the True Valence Mapper to enable relationship tracking. Without these core entities (`Person`, `Organization`), we cannot model connections.

## What Changes
- Define `Person` entity (name, title, bio).
- Define `Organization` entity (name, industry).
- Establish basic identifiers for these entities.

## Impact
- **Specs**: Creates new `entities` capability.
- **Code**: Will require new Supabase schema definitions and TypeScript interfaces (in future implementation steps).
