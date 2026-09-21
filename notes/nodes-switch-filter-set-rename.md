# Nodes: Switch, Filter, Set/Edit Fields, Rename Keys

## Switch — multi-way routing

- IF gives only two branches (true/false). When there are more than two
  categories, Switch replaces a chain of nested IF nodes with one node.
- Example: route an incoming email by subject — `invoice` → accounting,
  `lead` → sales, `complaint` → support, anything else → a **fallback
  output** (the default branch when no rule matches).
- Using several IF nodes instead of one Switch makes the workflow messy;
  Switch keeps routing logic in a single place.

## Filter — keep/discard, not branching

- Filter does not create multiple branches like IF/Switch. It evaluates a
  condition per item and splits the result into two outputs: **kept**
  (condition true) and **discarded** (condition false).
- Typical use: keep only items whose field matches a condition (e.g. a
  message that `contains` a keyword), drop the rest from the flow.
- Difference from IF: IF routes the *same* items down two different paths;
  Filter shrinks the item set along a single path.

## Set / Edit Fields — data transformation

- Adds, renames, or overwrites values on the JSON of each item.
- Two ways to fill a value:
  - **Fixed** — a literal, unchanging value (e.g. `"Hello Nikhil"`).
  - **Expression** — computed from the input, e.g. `{{ $json.name }}`, so
    each item gets a different value (mail-merge style).
- Good automation depends on clean, consistently-named data — this is the
  node used to normalize messy upstream field names before they reach
  Sheets/Notion/Gmail nodes.

## Rename Keys

- Changes only the **key name** of a field, not its value or type — e.g.
  `name` → `customerName`.
- Useful right after ingesting data with inconsistent or non-JSON-friendly
  key names (spaces, capitals) before passing it downstream.

## Quick comparison

| Node | Output shape | Use when |
| --- | --- | --- |
| IF | 2 branches, same items | Yes/no decision |
| Switch | N branches + fallback | 3+ categories |
| Filter | 1 branch, fewer items | Drop irrelevant items |
| Set/Edit Fields | Same items, new/changed values | Clean or enrich data |
| Rename Keys | Same items, renamed keys only | Fix field naming |
