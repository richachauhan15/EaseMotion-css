# Ease Word Carousel Component

A smooth, reusable word cycling animation component that cycles through multiple words vertically in place with fade and slide effects.

## Features

✅ Words scroll vertically in an `overflow:hidden` container  
✅ Each word fades/slides in then out  
✅ Loop through word array infinitely  
✅ Configurable speed via `--ease-carousel-speed` CSS variable  
✅ Responsive and accessible  
✅ Supports multiple speed variations  

## Usage

### Basic Structure

```html
<p>
    We are
    <span class="ease-word-carousel">
        <span class="carousel-word">innovative</span>
        <span class="carousel-word">creative</span>
        <span class="carousel-word">dynamic</span>
    </span>
</p>
```

### CSS Classes

- **`.ease-word-carousel`** - Container for the carousel (creates overflow hidden context)
- **`.carousel-word`** - Individual word element (must be direct child of container)

### CSS Variables

#### `--ease-carousel-speed`
The duration of the complete cycle for all words.

**Default:** `3s`

**Example:**
```css
.my-carousel {
    --ease-carousel-speed: 4s;
}
```

### Animation Details

- **Fade In:** Word fades in and slides up over the first 10% of the cycle
- **Display:** Word remains visible for the middle 75% of the cycle
- **Fade Out:** Word fades out and slides down over the final 15% of the cycle

## Examples

### Default Speed (3s cycle)
```html
<span class="ease-word-carousel">
    <span class="carousel-word">Word 1</span>
    <span class="carousel-word">Word 2</span>
    <span class="carousel-word">Word 3</span>
</span>
```

### Custom Speed (5s cycle)
```html
<span class="ease-word-carousel" style="--ease-carousel-speed: 5s;">
    <span class="carousel-word">Slow</span>
    <span class="carousel-word">Cycling</span>
    <span class="carousel-word">Words</span>
</span>
```

### Hero Tagline
```html
<h1>
    <span class="ease-word-carousel" style="--ease-carousel-speed: 4s;">
        <span class="carousel-word">Create</span>
        <span class="carousel-word">Inspire</span>
        <span class="carousel-word">Elevate</span>
    </span>
    beautiful animations
</h1>
```

## Accessibility

The component respects the `prefers-reduced-motion` media query. When enabled, animations are disabled and the first word is shown by default.

```css
@media (prefers-reduced-motion: reduce) {
    .carousel-word {
        animation: none;
        opacity: 1;
    }
}
```

## Customization

### Speed Presets

Create custom CSS classes for common speeds:

```css
.carousel-fast {
    --ease-carousel-speed: 2s;
}

.carousel-slow {
    --ease-carousel-speed: 5s;
}
```

### Styling

Style the words using standard CSS:

```css
.carousel-word {
    color: #667eea;
    font-weight: bold;
}
```

## Browser Support

- Chrome/Edge: ✅ Full support
- Firefox: ✅ Full support
- Safari: ✅ Full support
- Opera: ✅ Full support

All modern browsers with CSS animations and inline-block support.

## Integration

To add this component to EaseMotion CSS:

1. Create `components/ease-word-carousel.css` with the carousel styles
2. Import in `easemotion.css`:
   ```css
   @import "./components/ease-word-carousel.css";
   ```
3. Update documentation in the main README

## Tips

- Use an odd number of words for balanced timing between rotations
- Keep word lengths similar for a polished look
- Test with longer texts to ensure proper inline flow
- Consider the context—works great for hero sections and taglines

## License

MIT - Same as EaseMotion CSS