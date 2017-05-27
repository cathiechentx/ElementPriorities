# ElementPriorities

## Introduce

After we public [Proposal: Enhance HeroElement](https://discourse.wicg.io/t/proposal-enhance-heroelement/2163), we received an idea of element priorities suggested by @AshleyScirra is very interesting. Here are the Scenarios I thought about:

### Three Element Priorities
 1. High: Critical elements to users, like: elements display at first screen...
 2. Moderate: Default value.
 3. Low: Elements that usually users won't care, like: advertisement, license info, comments in some pages...

### Scenarios

With element priorities, we could optimize like this:

- Parse optimization:
	- High: Start layout immediately after this element loaded. (Speed up first screen paint)
	- Moderate: Layout after got N nodes, or layout after Ts parse period.
	- Low: Layout after got 2N nodes, or layout after 2Ts parse period.(Reduce whole page loading time.)

- Animations with priorities
	- Low：Pause these animations while they are out of viewport.

- Images with priorities
	- Priorities could be a hint to garbage collection.

- Text content with priorities
	- Low: No need to process [TextAutoSize](https://docs.google.com/document/d/1PPcEwAhXJJ1TQShor29KWB17KJJq7UJOM34oHwYP3Zg/edit#heading=h.kzw6s3kvr392).

- Others
	- Element priorities could be a hint to UA while it's optimizing.
