## GDG Finder ##

GDGs, or Google Developer Groups, are communities of developers that focus on Google technologies -
including Android - around the world. They host lots of different events like meetups, conferences,
study jams, and more! GDG Finder helps to locate GDGs around the world based on user's location.

The app has following features :

- Uses material themes and material design components like FAB and chips
- Follows material design guidelines
- Has support for RTL languages
- Has content descriptions for Talkback

## App Preview ##

<img src="https://github.com/pawanharariya/GDG-Finder/assets/43620548/710173f7-c2f8-4edd-9ac0-15683e2c95c5" alt="App Preview 1" width=180>
<img src="https://github.com/pawanharariya/GDG-Finder/assets/43620548/f615c8df-6354-4d09-9a09-d1e63f023d91" alt="App Preview 2" width=180>
<img src="https://github.com/pawanharariya/GDG-Finder/assets/43620548/ec264856-6e95-4aa1-a987-cebdf2297078" alt="App Preview 3" width=180>
<img src="https://github.com/pawanharariya/GDG-Finder/assets/43620548/98c54e2c-060b-4e37-8fe7-d9de2c00de11" alt="App Preview 4" width=180>

## Styling ##

Styling includes colors, fonts and text size. Android follows pyramid styling that has Theme at
bottom, Style above it and View on top.

### Theme ###

Themes are used to style every view of the app at once. Usually there are two themes - light and
dark. Themes can be used for following purposes :

1. Define default colors to the app. These default colors are automatically used by view like tabs
   or radio buttons to build a consistent style.

2. Set default font of the app.

3. Define general properties for all views.

### Style ###

Styles are re-usable styling information. It is small set of common designs to use throughout the
app. We define properties of a style and then apply it to a single view. For example text type for
all headers should be bold, so we define that in a style and then attach it to every view that is a
header.

### Attributes ###

These are properties of each view. They are not reusable so we have to define them for each view.
They are used for custom designing specific views as they are not common and applied to a single
view.

Every view uses a combination of all three - theme, style and attributes in increasing priority.
Attributes always override anything specified by a style or a theme, and style overrides theme.

## Design Aspects ###

1. Fonts, putting hints on edit texts or color of buttons.

2. Layout of screen and position of views. Focus should be drawn to important things. Present as
   much less as required, following information architecture.

3. Design based on use cases. A use case is task that a user might try to accomplish in the app.
   Example of one use case of Gmail app can be to receive and email, open it and then compose and
   send a reply. Every step of a use case should be simple and smooth. Taking feedback helps to
   improve the existing design.

4. **Accessibility** - The app's features should be accessible to a variety of users such as people
   with color blindness, vision impairment or users who interact using screen readers instead of
   touch.

## Fonts ##

Apps can download fonts at runtime using the downloadable fonts API. We can also ship fonts as part
of the apk itself, but its not recommended because it increases app size and makes it longer to
download and install. And, If the app uses the same font as some other app on the device, it is
downloaded only once.

## Material Design ##

Material design is a cross-platform design system from Google. It has a bunch of reusable components
and provide detailed specs for how text should be shown to how to layout out a screen.

### Theme attributes ###

Variables that point to different type of styling information like headline or primary color of the
app. It simplifies app styling like fonts and colors for material components because the styling is
applied to all the widgets, making the design consistent throughout the app. By default they follow
Material style, and we can extend them to customize the default style.

### Theme Overlays ###

It helps to override the existing theme, and applied to a subsection of the app, like the toolbar.
We use Theme Overlays to change the theme for some part (like making a dark toolbar) and continue to
using the main theme (light theme) for rest of the screen.

## Accessibility ## 

Accessibility means making the app for everyone, for example it should support right to left
languages like Arabic. The app's features should be accessible to a variety of people such as,
people with color blindness, vision impairment or users who interact using screen readers instead of
touch.

### RTL Languages ###

RTL languages display content from Right-to-Left direction, which is often called mirroring. Screen
assets like text, text-field icons, and icons with directions are mirrored. Numbers, icons without
direction, playback controls, charts and graphs are not mirrored. We should also declare that our
app supports RTL by defining in manifest. We can use following RTL APIs :

- android:layoutDirection
- android:textDirection
- android:textAlignment
- getLayoutDirectionFromLocale()

### Talkback and Content Descriptions ###

Talkback is an android app that reads what's on the screen, it helps people with visual impairment
to navigate through the app.

Content Descriptions are descriptive labels that explain the meaning of views. The Talkback uses
this to tell the user what the image is. They should be used for images, buttons and text views that
serve as labels. For EditTexts we can use hints, that are both visual elements and content
descriptors.

#### Content Grouping ####

For UI controls that Talkback should treat as a group, we can use content grouping. Related content
which is grouped together will be announced together. This helps to discover all the information on
screen without having to scan the screen again. This can be done why wrapping related views into a
view group.

#### Live Regions ####

We should change the content descriptions of buttons dynamically when the state changes. After,
changing the content description programmatically, we use Live Regions to tell Talkback that the
stuff is changed.

## Helpful Tips ##

1. Using `style` attribute for a material theme attributes, overrides the theme, since style has
   higher priority. So, using `style=?textAppearanceHeadline5` to a TextView will override the
   default font style of the app as Headline5 has its own font style. If we use `textAppearance`
   attribute instead, the default fonts is not overridden by the material
   style, `android:textAppearance="?textAppearanceHeadline5"`.

2. Use `dimens` and `colors` xml files to store all dimension and colors used throughout the app for
   consistent design. It also makes it easy to update these values.

3. Use `start` and `end` instead of `left` and `right`in layout properties, such as for paddings and
   margins.

4. Any resources in `res` folder can use qualifies. Qualifies are used to different resources based
   on language, country or screen size. Android then only loads the resources from the correct
   directory of each phone.

5. Use Accessibility scanner available on Play Store to get suggestions for improving accessibility
   of an app.

6. Use `-night` qualifiers to define resources like colors and drawables for night mode.