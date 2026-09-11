# Data-Model Atlas

## Authoritative content

Each entity must have a complete definition with all fields, types, nullability, PKs, FKs, and known uniqueness constraints. Cards may be compact, but the detail panel must show the entire table.

For every relationship, preserve source and target fields and cardinalities. A foreign key may reference a key other than `id` or be composite: derive the actual fields from the source. Distinguish uniqueness of a single field from uniqueness of a combination of fields.

Identify logical or polymorphic links as such; do not draw them as database-enforced foreign keys. If a cardinality cannot be determined from the source, mark it as unspecified. Keep isolated tables visible.

## Interface structure

**Left-hand list.**

- Search by table name or field name.
- Group or filter by functional area when the entity count makes this useful.
- Keep selection separate from visibility.
- Give each table an accessible show/hide toggle. Hiding an entity removes it and its relationships from the map while retaining its list entry.
- Make the sidebar collapsible, with a reopening control that remains reachable.

**Central canvas.**

- Readable cards with technical names, short functional descriptions, and compact content summaries.
- Table selection and highlighting of its relationships.
- A complete view and a control to isolate the selected table and its direct relationships.
- Background panning, zoom, and a “Fit” control.
- Dragging for each entity, with relationships updating during movement.
- A “Reset layout” control that restores the current view's layout.
- Relationship hover tooltips showing source and target tables and fields. Highlight the relationship and make the information available through keyboard interaction too.

**Right-hand detail panel.**

- Name, purpose, all fields, and relevant constraints.
- Incoming and outgoing relationships, with cardinality stated relative to the selected record.
- Navigation through FK fields and the relationship list.
- A panel that collapses independently of the left sidebar. With both closed, the map fills the released space.

These interactions define the atlas's reference shape. Adapt them to explicit requests or device constraints while preserving their purpose.

## Behaviors that make exploration reliable

**Hiding does not delete.** Toggles and filters affect presentation, not model data. Display a relationship only when both endpoints are visible. Counts distinguish the model total from entities and relationships visible in the current view.

**Dragging does not accidentally select.** Distinguish clicking from dragging using a small movement threshold. Account for zoom when calculating movement; dragging a card must not also pan the canvas.

**Positions remain useful.** Preserve manual positions through ordinary interactions within the same view, including hiding and showing a table. Views with different layouts, such as “All” and “Connected,” may retain separate arrangements. Persistence across page reloads is an additional choice; state it if implemented.

**Arrows follow the model.** During dragging, update paths, endpoints, and tooltips without rebuilding the entire UI or losing pointer capture. Handle self-references and multiple foreign keys between the same tables.

**Hover targets are reachable.** Provide a hit area wider than the visible line. Tooltips remain readable regardless of zoom, stay within the viewport, and disappear when the view changes or the map moves.

**Navigation preserves context.** If an FK leads to a table excluded by a filter, make the result understandable, for example by updating the filter. Respect an explicitly hidden table or make any restoration of its visibility clear. If every table in the view is hidden, explain how to show them again.

**Panels preserve the reader's work.** Closing and reopening a sidebar retains selection, filters, and visibility settings. The canvas adapts to the available space.

## Focused verification

Compare definitions against the source: complete entities, no omitted fields, and relationships with correct endpoints. Matching total counts alone does not establish equivalence.

In the browser, exercise this journey: search for a field, open its table, inspect all fields, isolate relationships, and follow a foreign key. Then check introduced or modified interactions: dragging at a zoom other than 100%, tooltips, hide/show toggles, and collapsible panels.

During updates, synchronize embedded data, descriptions, constraints, counts, and legends. Preserve existing interactive features; replacing model data must not regenerate an older version of the interface.
