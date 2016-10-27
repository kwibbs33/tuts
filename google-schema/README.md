### Info
* [http://schema.org/docs/schemas.html](http://schema.org/docs/schemas.html)
* [Google: structured data testing tool](http://google.com/webmasters/tools/richsnippets)


---

```html
<body>
  <main itemscope itemtype="http://schema.org/LocalBusiness">
		<section>
			<h1 itemprop="name">Cedar Gables Inn</h1>
			<p itemprop="telephone">(787) 517-1177</p>

			<a itemprop="url" href="http://www.cedargablesinn.com"></a>

			<div id="address" itemprop="address" itemscope itemtype="http://schema.org/PostalAddress">
				<div id="street" itemprop="streetAddress">486 Coombs St</div>
				<div id="locality" itemprop="addressLocality">Napa</div>
				<div id="region" itemprop="addressRegion">CA</div>
				<div id="postal" itemprop="postalCode">94559</div>
			</div>

			<div itemprop="aggregateRating" itemscope itemtype="http://schema.org/AggregateRating">
				Rated <span itemprop="ratingValue">3.5</span>/5
				<a href="#reviews" rel="nofollow"><span itemprop="reviewCount">2</span> reviews</a>
			</div>
		</section>

		<span class="hide" itemprop="geo" itemscope itemtype="http://schema.org/GeoCoordinates">
			<span class="latitude" itemprop="latitude">18.36844</span>
			<span class="longitude" itemprop="longitude">-66.179429</span>
		</span>

		<h2 itemprop="description">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Consectetur velit facilis quos nihil expedita consequuntur, numquam recusandae eius, praesentium quae vitae, unde ducimus, mollitia ullam error reprehenderit rem hic sed!</h2>
	</main>

	<!-- multiple reviews of a business don't work - you can easily add reviews for a product though -->
	<section id="reviews">
		<article>
			<h3 itemprop="author">Sarah Bettens</h3>
			<time itemprop="datePublished" datetime="2015-11-08">11/08/2015</time>
			<div itemprop="description" class="description">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dolores, ab, voluptas? Eligendi, provident, consequuntur placeat aliquam iste quidem magni veritatis voluptates pariatur voluptate neque laudantium expedita eum accusamus officiis sequi.</div>
		</article>
		<article>
			<h3 itemprop="author">Imogen Heap</h3>
			<time itemprop="datePublished" datetime="2016-03-21">3/21/2016</time>
			<div itemprop="description" class="description">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dolores, ab, voluptas? Eligendi, provident, consequuntur placeat aliquam iste quidem magni veritatis voluptates pariatur voluptate neque laudantium expedita eum accusamus officiis sequi.</div>
		</article>
	</section>
</body>
```
