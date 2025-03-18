# CSS

---
## scssVScss 

#### SCSS (Sassy CSS) is a superset of CSS, meaning it extends CSS with additional features like variables, mixins, inheritance, nesting, and more.
### To use SCSS - npm install -D sass

1. Variables: We can reuse them-
  ``` Typescript
  $primary-color: #3498db;
  .button {
  background-color: $primary-color;
```

2. Mixins: Allows you to define reusable blocks of styles called mixins. (We can consider them as CSS function blocks)
``` Typescript
@mixin border-radius($radius) {
  border-radius: $radius;
}

.button {
  @include border-radius(5px);
}
```
3. Partials and Imports: Allows you to break your styles into smaller, more manageable files using partials and then import them into a main SCSS file. We can import one sccs file to other files.
4. Nesting: SCSS allows you to nest CSS rules within one another, which can help to visually group related styles. 

---
