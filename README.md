# Video Assets for Health Equity Microsite

Site: [https://healthequity.aprnetwork.org/](https://healthequity.aprnetwork.org/)

This repository hosts all background and outro/join-us section videos used in the Webflow project. Videos are hosted via GitHub Pages as static assets to be referenced directly in Webflow using custom HTML `<video>` elements inside code embeds.

---

## Repository Structure

```
assets/
  Angela-background.mp4
  Fred-background.mp4
  Marcus-background.mp4
  family.mp4
  group.mp4
  parents.mp4
  picnic.mp4
  seniors.mp4

README.md
```

### Video Categories

**Character Background Videos**

* Angela-background.mp4
* Fred-background.mp4
* Marcus-background.mp4

**Join Us / Outro Frame Videos**

* family.mp4
* group.mp4
* parents.mp4
* picnic.mp4
* seniors.mp4

---

## Where These Videos Appear in Webflow

### Character Background Videos

Used in elements with the class:

* `.cover-video` inside `.character-background_wrapper`
  Characters include Angela, Fred, and Marcus.

These are implemented using Webflow **code embeds** containing `<video>` elements that reference GitHub Pages URLs.

### Join Us / Outro Frame Videos

Used in elements with the class:

* `.join-us_frame_video` inside `.join-us_outro`

Because different elements are shown or hidden at different breakpoints, multiple versions of each video exist. All `.join-us_frame_video` embeds should be checked and updated when replacing video sources.

---

## GitHub Pages URL Format

Videos are loaded from URLs following this pattern:

```
https://<username>.github.io/<repo-name>/assets/<filename>.mp4
```

Example:

```
https://yourusername.github.io/video-assets-repo/assets/Fred-background.mp4
```

Replace `<username>` and `<repo-name>` based on your repository.

---

## Updating Video Sources in Webflow

All video elements are implemented using custom code embeds. To update the video source:

1. In Webflow Designer, select the video element.
2. Click "Edit Custom Code" to open the code embed.
3. Update the `src` attribute in the `<source>` tag. Example:

```html
<video autoplay loop muted playsinline>
  <source src="https://<username>.github.io/<repo-name>/assets/Fred-background.mp4" type="video/mp4">
</video>
```

4. Save the embed and re-publish the site.
5. For outro videos, repeat this for all `.join-us_frame_video` elements across breakpoints.

---

## Replacing or Updating Videos

1. Replace the file in the `assets/` folder.

   * Keeping the same filename ensures all existing Webflow embeds continue working without changes.
2. Commit and push to `main`.
3. GitHub Pages will automatically serve the updated file at the same URL.
4. If filenames change, update every relevant code embed in Webflow.
5. Test all breakpoints because the outro section uses multiple hidden/shown versions of each video.

---

## Testing

Before publishing updates to the live site:

* Open each GitHub Pages video URL to confirm the video loads correctly.
* Verify autoplay, mute, loop, and playsinline behavior across browsers, including iOS.
* In Webflow, check that all `.join-us_frame_video` elements show the correct updated video at each breakpoint.

