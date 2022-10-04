# Flexbox



Flexbox is a one-dimensional layout method for arranging items in rows or columns.

* Items flex i.e expand the fill additional space or shrink to fit into smaller spaces.&#x20;

## Where to use Flexbox?

* Vertically centring a block of content inside its parent. Alternatively, use margin auto.&#x20;
* Making children take up equal width/height regardless of how much size is available.&#x20;
* Make all columns in a multi-column layout have the same height even if the amount of content varies.

## Adding Flexbox

### Example Scenario

<figure><img src="broken-reference" alt=""><figcaption></figcaption></figure>

```html
<body>
    <header>
        <h1>Sample flexbox example</h1>
    </header>
    
    <section>
        <article>
            <h2>First article</h2>
            <p>Tacos actually microdosing, pour-over semiotics banjo chicharrones retro fanny pack portland everyday carry vinyl typewriter. Tacos PBR&B pork belly, everyday carry ennui pickled sriracha normcore hashtag polaroid single-origin coffee cold-pressed. PBR&B tattooed trust fund twee, leggings salvia iPhone photo booth health goth gastropub hammock.</p>
        <article>
        
        <article>
        <h2>Second article</h2>
        <p>Tacos actually microdosing, pour-over semiotics banjo chicharrones retro fanny pack portland everyday carry vinyl typewriter. Tacos PBR&B pork belly, everyday carry ennui pickled sriracha normcore hashtag polaroid single-origin coffee cold-pressed. PBR&B tattooed trust fund twee, leggings salvia iPhone photo booth health goth gastropub hammock.</p>
      </article>

      <article>
        <h2>Third article</h2>
        <p>Tacos actually microdosing, pour-over semiotics banjo chicharrones retro fanny pack portland everyday carry vinyl typewriter. Tacos PBR&B pork belly, everyday carry ennui pickled sriracha normcore hashtag polaroid single-origin coffee cold-pressed. PBR&B tattooed trust fund twee, leggings salvia iPhone photo booth health goth gastropub hammock.</p>
        <p>Cray food truck brunch, XOXO +1 keffiyeh pickled chambray waistcoat ennui. Organic small batch paleo 8-bit. Intelligentsia umami wayfarers pickled, asymmetrical kombucha letterpress kitsch leggings cold-pressed squid chartreuse put a bird on it. Listicle pickled man bun cornhole heirloom art party.</p>
      </article>
    </section>
</body>
```

Turning section into a flexbox:

```css
section {
    display: flex;
}
```

<figure><img src="broken-reference" alt=""><figcaption></figcaption></figure>

#### Axis

*

    <figure><img src="broken-reference" alt=""><figcaption></figcaption></figure>
* The **main axis** is the axis running in the direction the flex items are laid out in (for example, as rows across the page, or columns down the page.)
* The start and end of this axis are called the **main start** and **main end**.
* The **cross axis** is the axis running perpendicular to the direction the flex items are laid out in.
* The start and end of this axis are called the **cross start** and **cross end**.

#### Flex Container

The parent element that has `display: flex` set on it (the `<section>` in our example) is called the **flex container**.

#### Flex Item

The items laid out as flexible boxes inside the flex container are called **flex items** (the `<article>` elements in our example).

## Flex Direction

* Flexbox provides a property called `flex-direction` that specifies which direction the main axis runs.
* This controls which direction the flexbox children are laid out in.
* By default this is set to `row.`
* This is why the previous example laied out the articles in rows.&#x20;

### Changing flex direction

```css
section {
    display: flex;
    flex-direction: column;
}
```

This restores the layout back to how it was without any flex.

<figure><img src="broken-reference" alt=""><figcaption></figcaption></figure>

### Flex Wrap

What if there are too many children inside a flex container?

Duplicating the articles several times in a flex container having main axis as row result in an overflow.

<figure><img src="broken-reference" alt=""><figcaption></figcaption></figure>

Flexbox allows us to wrap overflowing content.

```css
section {
    display: flex;
    flex-wrap: wrap;
}

article {
    flex: 200px;
}
```
