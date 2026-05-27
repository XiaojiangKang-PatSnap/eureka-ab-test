# Design System — PatSnap

## 1. Visual Theme & Atmosphere

PatSnap is a professional intelligence platform where data clarity and cognitive trust are the primary design values. The interface leads with **signal** — every visual decision reduces cognitive load and surfaces insight faster.

The design operates on a near-white canvas (`#F4F5F7`) with PatSnap Blue (`#0764E9`) as the primary brand accent. Typography uses **Inter** — a neutral, highly legible typeface. The neutral scale is built on a cool navy base (`#020A1A`). Semantic colors carry strict meaning: blue = action, green = success, orange = warning, red = error.

**Key Characteristics:**
- Near-white canvas (`#F4F5F7`) with PatSnap Blue (`#0764E9`) as primary action color
- Cool near-black (`#020A1A`) for text — precise, not warm
- Inter / system-ui — neutral, data-optimized typeface
- Subtle elevation: 1px borders + soft shadows, never decorative
- Outlined icon style, 1.5–2px stroke, `#495973` default color
- 4px base radius for components; 8px for cards; 50% for avatars
- Full dark mode support with `#020A1A` page background

---

## 2. Color Palette & Roles

### Primary Brand (Blue Theme — `#0764E9`)
| Token | Hex | Role |
|-------|-----|------|
| `--color-brand-primary` | `#0764E9` | Primary CTA, links, active states |
| `--color-brand-hover` | `#0456D1` | Hover state |
| `--color-brand-pressed` | `#0247B0` | Pressed/active state |
| `--color-brand-dark` | `#00369C` | Deep navy, high-emphasis |
| `--color-brand-light` | `#82C3FF` | Light blue tint |
| `--color-brand-subtle` | `#DDEBF8` | Tinted backgrounds, selected states |

### Semantic
| Token | Hex | Role |
|-------|-----|------|
| `--color-success` | `#45A321` | Positive signals |
| `--color-success-hover` | `#1D8820` | Hover |
| `--color-success-light` | `#B5DAA6` | Light green |
| `--color-success-subtle` | `#E3F1DE` | Success surface |
| `--color-warning` | `#DC7C08` | Caution, pending |
| `--color-warning-hover` | `#C26A05` | Hover |
| `--color-warning-light` | `#F1CB9C` | Light orange |
| `--color-warning-subtle` | `#FAECDA` | Warning surface |
| `--color-error` | `#D11A32` | Errors, alerts |
| `--color-error-hover` | `#B8172C` | Hover |
| `--color-error-light` | `#EDA3AD` | Light red |
| `--color-error-subtle` | `#F8DDE0` | Error surface |
| `--color-info` | `#1976D2` | Info states, secondary links |
| `--color-info-subtle` | `#DDEBF8` | Info surface |

### Extended Palette
| Token | Hex | Role |
|-------|-----|------|
| `--color-cyan` | `#27B4D1` | Teal accent, data series |
| `--color-cyan-dark` | `#008FAC` | Dark teal |
| `--color-cyan-subtle` | `#D4F0F6` | Teal surface |
| `--color-purple` | `#914AED` | Premium / AI features |
| `--color-purple-subtle` | `#E2D5ED` | Purple surface |
| `--color-yellow` | `#F7F28D` | Highlight / caution |

### Neutral Scale
| Token | Hex | Role |
|-------|-----|------|
| `--color-N900` | `#020A1A` | Text primary |
| `--color-N800` | `#344563` | Text dark |
| `--color-N700` | `#495973` | Text secondary, icon default |
| `--color-N600` | `#6B778C` | Text tertiary |
| `--color-N400` | `#8993A4` | Placeholder, disabled |
| `--color-N300` | `#B3BAC5` | Light gray |
| `--color-N200` | `#BCC2CC` | Border light |
| `--color-N100` | `#DFE1E6` | Border subtle, dividers |
| `--color-N50` | `#EBECF0` | Background tint |
| `--color-N20` | `#F4F5F7` | Page background |

### Surface & Elevation
| Token | Hex | Role |
|-------|-----|------|
| `--color-bg-page` | `#F4F5F7` | Page background |
| `--color-bg-card` | `#FFFFFF` | Card, panel surfaces |
| `--color-bg-overlay` | `rgba(2,10,26,0.45)` | Modal overlays |
| `--color-border-default` | `#DFE1E6` | Default borders, dividers |
| `--color-border-strong` | `#BCC2CC` | Emphasized borders |
| `--color-border-focus` | `#0764E9` | Focus ring |

### Dark Mode
| Token | Hex | Role |
|-------|-----|------|
| `--color-dark-bg-page` | `#020A1A` | Dark page background |
| `--color-dark-bg-card` | `#0D1B2E` | Dark card surface |
| `--color-dark-bg-elevated` | `#142236` | Elevated surface (dropdown, popover) |
| `--color-dark-bg-hover` | `#1A2A40` | Dark hover surface |
| `--color-dark-bg-input` | `#0A1525` | Input/form field background |
| `--color-dark-text-primary` | `#F4F5F7` | Primary text |
| `--color-dark-text-secondary` | `#C8CACD` | Secondary text |
| `--color-dark-text-tertiary` | `#60656F` | Tertiary text |
| `--color-dark-border` | `#DBDEE3` | Border |
| `--color-dark-border-subtle` | `#1E3048` | Subtle border (dividers) |
| `--color-dark-brand` | `#0764E9` | Brand blue (same) |
| `--color-dark-success` | `#45A321` | Success (same) |
| `--color-dark-success-light` | `#90DC67` | Success light (brighter for dark bg) |
| `--color-dark-warning` | `#DC7C08` | Warning (same) |
| `--color-dark-warning-light` | `#F0B85C` | Warning light |
| `--color-dark-error` | `#D11A32` | Error (same) |
| `--color-dark-error-light` | `#F6BBBA` | Error light |

**Dark mode component overrides:**
- Switch ON track: `#0764E9` (same as light)
- Checkbox/Radio checked: `#0764E9` (same as light)
- Card shadow: `0px 1px 2px rgba(0,0,0,0.20), 0px 4px 12px rgba(0,0,0,0.24)` (stronger for dark bg)
- Skeleton block: `#1A2A40` with shimmer `#243650`

---

## 3. Typography Rules

### Font Family

**International products (国外 / 产品内部):**
- **Primary**: `Inter`, fallbacks: `-apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", sans-serif`

**Domestic products (国内):**
- **Primary**: `"PingFang SC", "Microsoft YaHei", "Hiragino Sans GB", "WenQuanYi Micro Hei", sans-serif`

**Monospace** (patent numbers, IDs, codes): `"JetBrains Mono", "Fira Code", "Courier New", monospace`

**Weights used**: 400 (Regular) and 600 (Bold) only — per spec

### Size & Line Height Scale (from spec)
| Size | Weight | Line Height | Line Height (loose) | Usage |
|------|--------|-------------|---------------------|-------|
| 12px | 400/600 | 16px | — | Caption, small label, tag |
| 14px | 400/600 | 20px | 26px | Body, form labels, component labels ★ |
| 16px | 400/600 | 24px | — | Sub-heading |
| 18px | 400/600 | 24px | — | Section heading |
| 20px | 400/600 | 28px | — | Page heading |
| 24px | 400/600 | 32px | — | Large heading |
| 36px | 400/600 | 48px | — | Display / hero |

> ★ 14px is the most common size. It uniquely has two line-height options: 20px (tight, for UI components) and 26px (loose, for body reading).

### Principles
- Only two weights: **400** (regular) and **600** (bold). No 300, no 500, no 700.
- 14px / 400 / lh 20px is the default component text size.
- Monospace for all patent numbers, IDs, and codes.

---
## 4. Component Specifications

### 4.1 Button 按钮

**5 types:**

| Type | Description |
|------|-------------|
| Primary 首要按钮 | Brand color, main CTA |
| Secondary 次要按钮 | Outlined, secondary action |
| Tertiary 三级按钮 | Ghost/text, low-emphasis |
| Ghost 幽灵按钮 | Transparent bg, border only |
| Warning 警告按钮 | Red, destructive actions — universal across all products |

**States:** Normal → Hover → Pressed (each type). Disabled state disables hover entirely.

**Sizes (5 levels):**

| Size | Label | Height |
|------|-------|--------|
| XL | 超大按钮 | 48px |
| L | 大按钮 | 40px |
| Default | 默认尺寸 | 32px |
| S | 小按钮 | 28px |
| XS | 紧凑布局 | 24px |

**Shapes:** Rectangle (default) · Full rounded (全圆角, use sparingly) · Icon-only circle

**Colors:**

| Type | Normal bg | Normal text | Hover bg | Pressed bg |
|------|-----------|-------------|----------|------------|
| Primary | `#0764E9` | `#FFFFFF` | `#0456D1` | `#0247B0` |
| Secondary | `#FFFFFF` | `#495973` | border `#0764E9`, text `#0764E9` | — |
| Tertiary / Ghost | transparent | `#0764E9` | `#DDEBF8` | — |
| Warning | `#D11A32` | `#FFFFFF` | `#B8172C` | — |
| Disabled (all) | `#EBECF0` | `#8993A4` | — | — |

**Specs:**
- Font: 14px Inter weight 600
- Radius: 4px (rectangle) / 50% (full-round)
- Focus ring: `0 0 0 3px rgba(7,100,233,0.25)`
- Icon + text can collapse to icon-only in compact layouts

---

### 4.2 Input 输入框

**Variants:** Input (single-line) · Textarea (multi-line)

**Sizes:**
- Large: height **48px** (`extract-big-48` token)
- Default: height **32px**
- Mini: height **24px** (compact layouts)

**States:**

| State | Border | Background | Shadow |
|-------|--------|------------|--------|
| Default | `1px solid #DFE1E6` | `#FFFFFF` | none |
| Hover | `1px solid #BCC2CC` | `#FFFFFF` | none |
| Focus / Active | `1px solid #0764E9` | `#FFFFFF` | `0 0 0 3px rgba(7,100,233,0.15)` |
| Disabled | `1px solid #DFE1E6` | `#F4F5F7` | none |
| Error | `1px solid #D11A32` | `#FFFFFF` | `0 0 0 3px rgba(209,26,50,0.15)` |

- Placeholder: `#8993A4`
- Input text: `#020A1A`, 14px weight 400
- Error message: wraps below input, `#D11A32`, 12px
- Radius: 4px

---

### 4.3 Tag 标签

**Usage:** Mark attributes/dimensions; categorization and filtering.

**Sizes:**
| Size | Height |
|------|--------|
| Large 大 | 32px |
| Medium 中 | 24px |
| Small 小 | 20px |

**Visual styles (4 types):**

| Style | Background | Text | Border |
|-------|-----------|------|--------|
| Dark 深色 | `#495973` | `#FFFFFF` | none |
| Light 浅色 | `#DDEBF8` | `#0764E9` | none |
| Outlined 描边 | `#FFFFFF` | `#495973` | `1px solid #DFE1E6` |
| Gray 灰色 | `#EBECF0` | `#495973` | none |

**States:** Normal · Hover (each style has hover variant)

**Rules:**
- Truncated text → show tooltip on hover with full text
- Tag with link text → show underline on hover
- 3 padding options available
- Radius: 4px

---

### 4.4 Alert 警告提示

**4 types:**

| Type | Background | Border-left color | Border-left width | Icon color |
|------|-----------|-------------------|-------------------|------------|
| Success | `#E3F1DE` | `#45A321` | 3px | `#45A321` |
| Warning | `#FAECDA` | `#DC7C08` | 3px | `#DC7C08` |
| Error | `#F8DDE0` | `#D11A32` | 3px | `#D11A32` |
| Info | `#DDEBF8` | `#0764E9` | 3px | `#0764E9` |

**Layout modes:** Banner/inline (full-width) · Card/block (contained)

**Configurable options:**
- With / without icon
- With / without close (×) button
- With / without action button or link
- Title only, or title + description

**Rules:**
- Icon left-aligned, vertically centered with first line of text
- Persistent if no close button; dismissible if close button present

---

### 4.5 Checkbox 多选框

**Usage:** Multiple selections; state marking requiring submit action (vs Switch which is immediate).

**States (6):** Unchecked · Hover unchecked · Checked · Indeterminate · Disabled checked · Disabled indeterminate

**Dimensions:**
| Property | Value |
|----------|-------|
| Box size | 14 × 14px |
| Shape | Rectangle |
| Border radius | 3px |
| Border width | 1.5px |
| Checkmark stroke | 2px |
| Label gap | 8px |
| Label font | 14px / lh 20px |

**Colors:**
| State | Background | Border |
|-------|-----------|--------|
| Unchecked | `#FFFFFF` | `#BCC2CC` |
| Hover unchecked | `#FFFFFF` | `#0764E9` |
| Checked / Indeterminate | `#0764E9` | `#0764E9` |
| Disabled unchecked | `#F4F5F7` | `#DFE1E6` |
| Disabled checked | `#DDEBF8` | `#DDEBF8` |

**Layout:** Long text wraps; checkbox aligns with first line of text.

---

### 4.6 Radio 单选框

**Usage:** Single selection from multiple choices. Show all options by default (use Select when too many options).

**States (4):** Selected · Unselected · Hover unselected · Disabled selected

**Dimensions:**
| Property | Value |
|----------|-------|
| Size | 16 × 16px |
| Shape | Circle |
| Border width | 1.5px |
| Label gap | 8px |
| Label font | 14px / lh 20px |

**Colors:**
| State | Background | Border |
|-------|-----------|--------|
| Unselected | `#FFFFFF` | `#BCC2CC` |
| Hover unselected | `#FFFFFF` | `#0764E9` |
| Selected | `#0764E9` | `#0764E9` |
| Disabled | `#F4F5F7` | `#DFE1E6` |

**Layout:** Long text wraps; radio aligns with first line of text. Group layout: fixed-width columns or fixed-gap — choose per context.

---

### 4.7 Switch 开关

**Usage:** Toggle between two opposing states; triggers immediate change (vs Checkbox which requires submit).

**Sizes:**
| Size | Dimensions |
|------|-----------|
| Regular 常规 | 32 × 20px |
| With text 含文字 | variable width × 20px |
| Small 小尺寸 | 22 × 14px |

> With-text switch: width fixed to the wider of the two state labels — prevents width change on toggle (important for multilingual).

**Colors:**
| State | Track color |
|-------|------------|
| ON | `#0764E9` (brand blue) |
| OFF | `#DFE1E6` |
| ON disabled | `#0764E9` @ 60% opacity |
| OFF disabled | `#DFE1E6` @ 60% opacity |
| Knob (thumb) | `#FFFFFF` |

**Knob shadow:** `0px 1px 2px rgba(0,0,0,0.08)`

**Spacing (knob to edge):** Regular: 2px · Small: 1.5px

---

### 4.8 Tab 标签页

**Usage:** Organize parallel content categories; switching tabs does not navigate to a new page.

**3 types:**
| Type | Usage |
|------|-------|
| Line 线型 | Top-level navigation, primary entry |
| Card 卡片型 | Secondary navigation, sub-pages |
| Capsule 胶囊型 | Tertiary, filter-style |

**3 sizes:** Small (compact) · Medium (default) · Large (with icon, top-level nav)

**States per tab item:** Normal · Hover · Active/Selected · Disabled

**Rules:**
- Universal entry points: use tabs with icons
- Sub-level navigation: text-only tabs
- Supports close (×) button variant

---

### 4.9 Pagination 分页

**2 styles:**
| Style | Description |
|-------|-------------|
| Default 默认 | Full pagination with page numbers |
| Simple 简洁 | Prev/Next only with current page input |

**Page number logic:**
- Maximum **7 positions** shown in middle section
- Ellipsis (`…`) when page count exceeds display window
- Examples: `← 1 2 3 4 →` · `← 1 2 3 4 5 6 7 →` · `← 1 2 3 4 5 … 20 →` · `← 1 … 4 5 6 … 20 →`

**Colors:**
| State | Background | Text | Border | Height |
|-------|-----------|------|--------|--------|
| Current page | `#DDEBF8` | `#0764E9` weight 600 | `1px solid #0764E9` | 32px |
| Normal page | transparent | `#495973` | `1px solid #DFE1E6` | 32px |
| Hover page | `#F4F5F7` | `#020A1A` | — | 32px |
| Disabled arrow | — | `#BCC2CC` | — | 32px |

- Radius: 4px per button
- Min button width: 32px
- Button gap: 4px
- Font: 14px weight 400 (current page weight 600)
- **Single page rule:** Hide entire pagination when only 1 page exists (`hide-on-single-page`)

**Optional modules:**
| Module | Default options |
|--------|----------------|
| Total count | — |
| Go-to input | Enter or click to jump; clamps to valid range |
| Page size selector | 10, 20, 50, 100 per page |

---

### 4.10 Dropdown 下拉

**2 border styles:** Bordered (带边框) · Borderless (不带边框, text + arrow only)

**States:** Normal (▾) · Open (▲, layer visible) · Option hover · Option selected

**Rules:**
- Default layer width = trigger button width (minimum)
- Arrow rotates on open
- Selected result carried back into trigger label by default (configurable)
- Default trigger: click (configurable to hover)
- **One size only** — no large/small variants

**Metric selection card variant (指标选择卡片):**
- Two panels: System fields (系统字段) + Custom fields (自定义字段)
- Left panel: categorized list (Number, Patent Fields, Date, etc.)
- Selected items shown with checkmark

---

### 4.11 Dialog 弹窗

**Structure:**
```
┌─────────────────────────────┐
│ Title                    ×  │  ← Header
├─────────────────────────────┤
│  Body content               │  ← Content area
├─────────────────────────────┤
│              Cancel  Confirm│  ← Footer
└─────────────────────────────┘
```

**Size variants:**

| Size | Width | Usage |
|------|-------|-------|
| S | 480px | Simple confirm, short form |
| M | 640px | Standard dialog (default) |
| L | 800px | Complex form, multi-column content |
| XL | 960px | Data-heavy content, wide tables |
| Fullscreen | 100vw × 100vh | Immersive editing, full-page workflow |

**Colors:**
- Background: `#FFFFFF`
- Overlay mask: `rgba(2,10,26,0.45)`
- Header border-bottom: `1px solid #DFE1E6`
- Footer border-top: `1px solid #DFE1E6`
- Radius: 8px
- Shadow: `0px 12px 40px rgba(2,10,26,0.16)`

---

### 4.12 Notification 通知提醒

**Usage:** In-app message delivery; strong interruption — use sparingly.

**4 positions:** `top-right` (default) · `top-left` · `bottom-right` · `bottom-left`

**Configurable variants:**
1. Default (title + body)
2. With close button (default has close ×)
3. With icon / without icon
4. With action button / with action link
5. Rich content (custom body)

**Minimum unit:** Compact form (no action, no extra content) — content cannot go smaller.

**Dimensions:**
- Width: 320px (fixed)
- Padding: 16px
- Title font: 14px weight 600
- Body font: 14px weight 400, `#495973`
- Radius: 8px
- Offset from viewport edge: 24px
- Stack gap (multiple notifications): 12px

**Auto-dismiss:**
- Default duration: 4.5 seconds
- Customizable; set to 0 for persistent (manual close only)

**Colors:**
- Background: `#FFFFFF`
- Border: `1px solid #DFE1E6`
- Shadow: `0px 4px 16px rgba(2,10,26,0.10)`
- Info tint bg: `#DDEBF8`
- Success tint bg: `#E3F1DE`
- Warning tint bg: `#FAECDA`
- Error tint bg: `#F8DDE0`

---

### 4.13 Popconfirm 气泡确认框

**Usage:** Lightweight confirmation in popover format. Simpler than Dialog. Use for: delete confirmation, irreversible actions.

**Structure:**
```
┌──────────────────────────────┐
│ ⚠ Are you sure?              │
│              [Cancel] [OK]   │
└──────────────────────────────┘
      ▲ (arrow to trigger)
```

**Arrow positions:** Top · Bottom · Left · Right · Top-left · Top-right · Bottom-left · Bottom-right

**Colors:**
- Background: `#FFFFFF`
- Border: `1px solid #DFE1E6`
- Shadow: `0px 4px 16px rgba(2,10,26,0.10)`
- Radius: 8px
- Warning icon: `#DC7C08`

**Fully customizable:** icon, title, body, button labels.

---

### 4.14 Form 表单

**3 layout modes:**
| Mode | Description |
|------|-------------|
| Horizontal 水平 | Label left, input right (inline) |
| Vertical 垂直 | Label above input |
| Inline 行内 | All fields in one row |

**Form item structure:**
```
Label *        [________________]
               Helper text / error message
```

- Required fields: `*` asterisk
- Error message below input: `#D11A32`, 12px
- Label alignment (horizontal): left-aligned or right-aligned

**Validation triggers:** blur · change · submit

**Supported controls:** Input · Select · Checkbox · Radio · Switch · DatePicker · Textarea · Number input · Custom

**Button placement:**
- Horizontal: buttons align with input column (not label column)
- Inline: buttons inline with fields
- Common combinations: Save + Cancel · Save + Cancel + Reset

---

### 4.15 Toast

**4 types:**
| Type | Background | Icon color | Text color |
|------|-----------|------------|------------|
| Success | `#E3F1DE` | `#45A321` | `#020A1A` |
| Warning | `#FAECDA` | `#DC7C08` | `#020A1A` |
| Error | `#F8DDE0` | `#D11A32` | `#020A1A` |
| Info | `#DDEBF8` | `#0764E9` | `#020A1A` |

**Rules:**
- Close button: optional, **default is with close button**
- Max width: **1000px**
- Default duration: **3 seconds** (customizable)
- Supports redirect/jump links

---

### 4.16 Skeleton 骨架屏

**2 modes:**
| Mode | Description |
|------|-------------|
| Static 静态 | Non-animated gray blocks |
| Animated 动态 | Shimmer/pulse animation |

**Colors:**
- Skeleton block: `#E0E0E0` / `#D0D0D0`
- Background: `#F4F5F7`

**Usage:** Placeholder while content loads. Mimics shape and layout of actual content (card, list, table rows).

---

### 4.17 Tooltips

| Variant | Background | Border | Text |
|---------|-----------|--------|------|
| Default | `#F4F5F7` | `#CFD3DA` | `#495973` |
| Success | `#E3F1DE` | `#45A321` | `#1D8820` |
| Error | `#F8DDE0` | `#D11A32` | `#D11A32` |
| Warning | `#FAECDA` | `#DC7C08` | `#DC7C08` |
| Info | `#DDEBF8` | `#0764E9` | `#1976D2` |

- Radius: 4px · Padding: 8px 12px · Font: 12px weight 400

**Arrow placements (12 positions):**

| Group | Positions |
|-------|-----------|
| Top | `top-start` · `top` · `top-end` |
| Bottom | `bottom-start` · `bottom` · `bottom-end` |
| Left | `left-start` · `left` · `left-end` |
| Right | `right-start` · `right` · `right-end` |

- Arrow size: 6px
- Offset from edge: 12px (for start/end variants)

---

### 4.18 Cards & Panels

- Background: `#FFFFFF`
- Border: `1px solid #DFE1E6`
- Radius: 8px
- Shadow: `0px 1px 2px rgba(2,10,26,0.04), 0px 4px 12px rgba(2,10,26,0.06)`
- Hover: shadow `0px 4px 16px rgba(2,10,26,0.10)`, border `#82C3FF`

---

### 4.19 Data Tables

- Header: `#FAFBFC` bg · `#8993A4` text · 12px weight 600 uppercase
- Row hover: `#B3BAC5` (N300, neutral gray)
- Border: `1px solid #DFE1E6` horizontal only
- Selected row: `#DDEBF8` bg + `2px solid #0764E9` left border
- Cell text: 14px `#495973`

---

### 4.20 Icons

- Style: outlined / line, 1.5–2px stroke
- Sizes: 16px · 20px · 24px
- Default: `#495973` · Hover/active: `#0764E9` · Disabled: `#8993A4` · Error: `#D11A32`

**Grid system:**

| Size | Grid | Live area | Padding |
|------|------|-----------|---------|
| 24px | 24 × 24px | 20 × 20px | 2px |
| 20px | 20 × 20px | 16 × 16px | 2px |
| 16px | 16 × 16px | 14 × 14px | 1px |

- Pixel-aligned strokes; no half-pixel values
- Corner radius on icon shapes: 1px (small details) / 2px (larger shapes)
- Consistent optical weight across the set

---

### 4.21 Navigation

- Sidebar: `#FFFFFF` bg · `1px solid #DFE1E6` right border · 240px (collapsed: 64px)
- Active item: `#DDEBF8` bg · `#0764E9` text+icon · `3px solid #0764E9` left border
- Top bar: `#FFFFFF` · `1px solid #DFE1E6` bottom border

---
## 5. Data Visualization

### Chart Types

| Type | Chinese | Usage |
|------|---------|-------|
| Bar | 柱状图 | Categorical comparison |
| Line | 折线图 | Trend over time |
| Area | 面积图 | Volume trend, stacked composition |
| Pie / Donut | 饼图 / 环形图 | Part-to-whole (≤6 slices recommended) |
| Scatter | 散点图 | Correlation, distribution |
| Combo | 组合图 | Dual-axis, bar + line overlay |
| Funnel | 漏斗图 | Conversion flow |
| Radar | 雷达图 | Multi-dimensional comparison |
| Heatmap | 热力图 | Density, matrix values |
| Treemap | 树图 | Hierarchical proportion |
| Sankey | 桑基图 | Flow and relationship |

### Chart Color Palette (ordered)
| Order | Hex | Name |
|-------|-----|------|
| 1 | `#1976D2` | Blue (primary series) |
| 2 | `#43B74B` | Green |
| 3 | `#FABB27` | Yellow |
| 4 | `#FD865A` | Orange |
| 5 | `#95D0F7` | Light blue |
| 6 | `#7B61FF` | Purple |
| 7 | `#27B4D1` | Teal |
| 8 | `#A2C716` | Yellow-green |
| 9 | `#E96A94` | Pink |
| 10 | `#CA6B48` | Dark orange |

### Chart Component Specs

| Element | Spec |
|---------|------|
| Axis label | 12px weight 400, `#8993A4` |
| Axis line | 1px `#DFE1E6` |
| Grid line (light) | 1px dashed `#DFE1E6` |
| Grid line (dark) | 1px dashed `#1A2A40` |
| Tick mark | 4px, `#DFE1E6` |
| Legend text | 12px weight 400, `#495973` |
| Legend indicator | 8px circle or square, matches series color |
| Tooltip bg | `#FFFFFF`, shadow `0px 4px 12px rgba(2,10,26,0.10)` |
| Tooltip text | 12px weight 400, `#495973`; value weight 600 |
| Tooltip radius | 4px |
| Chart default text | `#495973` |

### Chart Rules
- Dark chart background: `#061632`
- Always include data labels or tooltips — never rely on color alone
- Sequential palette: `#0764E9` → `#82C3FF` → `#DDEBF8`
- Diverging palette: `#D11A32` ← neutral → `#45A321`
- Pie/Donut: max 6 slices; group remaining into "Other"
- Bar chart: minimum bar width 12px; gap ratio 0.3–0.5
- Line chart: stroke width 2px; data point dot 4px radius on hover

---

## 6. Layout Principles

### Spacing System
- Base unit: **4px**
- Scale: 4, 8, 12, 16, 20, 24, 32, 40, 48, 64, 80, 96px

### Grid & Container
- Sidebar: 240px fixed (collapsed: 64px)
- Content area: fluid, max-width 1440px
- Page padding: 24px horizontal, 24px vertical
- Card grid: 12-column, 16px gutter
- Dashboard widgets: 4-col (3-col tablet, 1-col mobile)

### Border Radius Scale
| Value | Use |
|-------|-----|
| 2px | Progress bars, internal dividers |
| 4px | Buttons, inputs, tags, tooltips, pagination |
| 8px | Cards, panels, modals, dialogs |
| 12px | Feature cards, hero panels |
| 50% | Avatars, icon buttons |

### Whitespace Philosophy
- Dense data: generous padding within components (16–24px)
- Section separation: 32–48px vertical gap
- Tables/lists: tighter row padding (8–12px) — users scan, not read

---

## 7. Depth & Elevation

| Level | Shadow | Use |
|-------|--------|-----|
| Flat (0) | none | Page bg, table rows |
| Raised (1) | `0px 1px 2px rgba(2,10,26,0.04), 0px 4px 12px rgba(2,10,26,0.06)` | Cards, panels |
| Floating (2) | `0px 4px 16px rgba(2,10,26,0.10), 0px 8px 24px rgba(2,10,26,0.08)` | Dropdowns, popovers, notifications |
| Modal (3) | `0px 12px 40px rgba(2,10,26,0.16)` | Modals, dialogs, drawers |
| Focus Ring | `0 0 0 3px rgba(7,100,233,0.25)` | Focused interactive elements |

Shadows use cool navy tint `rgba(2,10,26,*)` — functional only, never decorative.

---

## 8. Do's and Don'ts

### Do
- Use `#020A1A` for text — never pure `#000000`
- Apply `#0764E9` only for primary actions and active states
- Use only weight 400 and 600 — per spec
- Apply semantic colors consistently: blue = action, green = success, orange = warning, red = error
- Use 1px borders (`#DFE1E6`) for structure instead of heavy shadows
- Use monospace for patent numbers, IDs, codes
- Maintain 4px spacing grid
- Hide pagination when only 1 page exists
- Switch ON color = `#0764E9` (brand blue, not green)

### Don't
- Don't use pure `#000000` for text
- Don't fill large surfaces with `#0764E9`
- Don't use decorative shadows
- Don't mix semantic colors
- Don't use weight 300, 500, or 700 — only 400 and 600
- Don't use 0px radius on interactive elements (minimum 4px)
- Don't introduce chart colors outside the 10-color palette
- Don't show pagination on single-page results

---

## 9. Responsive Behavior

### Breakpoints
| Name | Width | Key Changes |
|------|-------|-------------|
| Mobile | < 768px | Single column, bottom nav, collapsed sidebar |
| Tablet | 768–1024px | 2-column grid, icon-only sidebar |
| Desktop Small | 1024–1280px | 3-column grid, full sidebar |
| Desktop | 1280–1440px | 4-column grid, full layout |
| Large Desktop | > 1440px | Max-width container, centered |

### Collapsing Strategy
- Sidebar: full labels → icon-only → bottom tab bar
- Tables: horizontal scroll on mobile, priority columns only
- Dashboard: 4-col → 2-col → 1-col
- Charts: simplified labels, larger touch targets on mobile

---

## 10. Agent Prompt Guide

### Quick Color Reference
- Page bg: `#F4F5F7` · Card bg: `#FFFFFF`
- Primary text: `#020A1A` · Secondary: `#495973` · Tertiary: `#6B778C`
- Brand blue: `#0764E9` · Hover: `#0456D1` · Subtle: `#DDEBF8`
- Border: `#DFE1E6` · Card shadow: `0px 1px 2px rgba(2,10,26,0.04), 0px 4px 12px rgba(2,10,26,0.06)`
- Success: `#45A321` / `#E3F1DE` · Warning: `#DC7C08` / `#FAECDA` · Error: `#D11A32` / `#F8DDE0`

### Quick Font Reference
- International: `Inter` · Domestic: `PingFang SC, Microsoft YaHei`
- Weights: 400 (regular) and 600 (bold) only
- Default body: 14px / lh 20px · Loose body: 14px / lh 26px

### Example Component Prompts
- **Button**: `#0764E9` bg, white text, 4px radius, 14px weight 600, hover `#0456D1`, focus ring `0 0 0 3px rgba(7,100,233,0.25)`, default height 32px
- **Input**: white bg, `1px solid #DFE1E6`, 4px radius, focus border `#0764E9` + shadow `0 0 0 3px rgba(7,100,233,0.15)`, placeholder `#8993A4`, default height 32px
- **Card**: white bg, `1px solid #DFE1E6`, 8px radius, card shadow, hover border `#82C3FF`
- **Tag (light)**: `#DDEBF8` bg, `#0764E9` text, 4px radius, 12px weight 600
- **Alert (warning)**: `#FAECDA` bg, `#DC7C08` left border 3px, icon `#DC7C08`
- **Table**: `#FAFBFC` header, 12px weight 600 uppercase `#8993A4`, row hover `#B3BAC5`, horizontal borders `#DFE1E6`
- **Pagination**: active `#DDEBF8` bg + `1px solid #0764E9` + `#0764E9` text weight 600; inactive `#8993A4`; 4px radius; 32px height
- **Switch ON**: `#0764E9` track, white knob, shadow `0px 1px 2px rgba(0,0,0,0.08)`
- **Toast (success)**: `#E3F1DE` bg, `#45A321` icon, `#020A1A` text, max-width 1000px, 3s default
- **Dialog**: white bg, 8px radius, overlay `rgba(2,10,26,0.45)`, shadow `0px 12px 40px rgba(2,10,26,0.16)`, default width 640px
- **Tooltip**: `#F4F5F7` bg, `#CFD3DA` border, 4px radius, 12px weight 400, 12 arrow positions
- **Notification**: white bg, 320px width, 8px radius, shadow `0px 4px 16px rgba(2,10,26,0.10)`, 4.5s auto-dismiss
- **Chart**: primary series `#1976D2`, 10-color palette, axis label 12px `#8993A4`, tooltip white bg 4px radius

### Iteration Guide
1. `#F4F5F7` page bg — white cards float naturally
2. `#0764E9` is the trust signal — primary actions only
3. `#020A1A` text — cool precision for a data product
4. Weight 400 (body) and 600 (emphasis/headings) only
5. 1px borders + subtle shadows — structure through line
6. Semantic colors carry strict meaning — never repurpose
7. 4px spacing grid — data interfaces demand precision
8. Dark mode: `#020A1A` base, same semantic colors
9. International vs domestic font stacks — choose per product region
10. Icon grid: outlined style, 1.5–2px stroke, pixel-aligned
