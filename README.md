# FoodFlow UI Component System

A dependency-free production-style frontend based on the supplied food delivery dashboard direction.

## Component Architecture

- Design system: tokens for color, spacing, radius, shadows, focus rings, and breakpoints.
- UI primitives: Button, IconButton, Chip, Badge, Panel, Skeleton, EmptyState.
- Domain components: SearchBar, ActiveOrder, CategoryGrid, StoreCard, ProductCard, WalletPanel, NotificationList, OrderAgainItem, StoreFilters.
- Composition layer: dashboard state coordinates loading, filtering, sorting, empty results, and responsive layout.

## Props / API Design

```ts
type StoreCardProps = {
  id: number;
  name: string;
  cuisine: string;
  rating: number;
  eta: number;
  fee: number;
  icon: IconName;
  badge?: string;
  open: boolean;
  favorite: boolean;
  freeDelivery: boolean;
  promos: boolean;
};

type ProductCardProps = {
  name: string;
  restaurant: string;
  price: number;
  icon: IconName;
};

type FilterProps<T> = {
  id: string;
  label: string;
  predicate: (item: T) => boolean;
};
```

## Usage Examples

```js
renderStoreCard({
  id: 6,
  name: 'Suya Republic',
  cuisine: 'BBQ · Nigerian',
  rating: 4.9,
  eta: 15,
  fee: 0,
  icon: 'suya',
  badge: 'Free delivery',
  open: true,
  favorite: false,
  freeDelivery: true,
  promos: false,
});
```

## Production Practices Included

- Semantic landmarks and accessible labels.
- Keyboard-visible focus states.
- aria-live regions for dynamic store results.
- Loading skeletons before data resolves.
- Empty state for no-result search or filter combinations.
- Edge cases for closed stores, saved stores, zero-fee delivery, promos, long names, and unread notifications.
- Mobile, tablet, and desktop responsive layouts.
- Reduced-motion support.
- Data-driven components that can be lifted into React, Vue, Svelte, or server-rendered templates.
