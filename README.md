# Coming Soon / Newsletter

A basic coming soon or subscribe to newsletter page with a resumé above the input to subscribe yourself.

## 👥 For who is this page

This page is made for those people who:

- Want to create a blog or have their own newsletter.
- Want to start a business or an idea and needs a comingsoon page.

It helps them to have a page instantly just forking the project or taking the source code.

## 📈 Metrics centric

I've wanted to build a fast page with a beautiful design so the user could have a good user experience.
I know there is room for improvement, but this is quite good for a first iteration as we can see.

![Metrics by Lighthouse](https://github.com/tureey/comingsoon-landing-page/blob/master/docs/lighthouse.png)

## 👩🏽‍🎨 How to customize

There are a few thinks to customize:

- Color palette
- Pattern of the header
- Manifest.json (for PWA)
- (Not done yet) Where to send the email you want to store

### 🎨 ‍‍Color palette

I'm following the structure I use in all the projects:

```
const theme = {
  palette: {
    primary: {
      // green
      900: "hsl(125, 73%, 20%)",
      700: "hsl(122, 39%, 41%)", // hover, focus, selected effects
      500: "hsl(123, 35%, 51%)", // Buttons, Badges, borders...
      300: "hsl(126, 49%, 84%)",
      100: "hsl(125, 65%, 93%)", // Notifications/labels background
    },
    grey: {
      900: "hsl(0, 0%, 23%)", // Titles
      700: "hsl(0, 0%, 38%)", // Paragraphs, ...
      600: "hsl(0, 0%, 49%)", // Disabled button text-color
      500: "hsl(0, 0%, 62%)", // Some details
      300: "hsl(0, 0%, 81%)", // Disabled button bg
      200: "hsl(0, 0%, 91%)", // Footers of modals, background of other sections...
      100: "hsl(0, 0%, 97%)", // Background
    },
    accent: {
      red: {
        900: "hsl(360, 85%, 25%)",
        700: "hsl(360, 67%, 44%)", // hover, focus, selected effects
        500: "hsl(360, 64%, 55%)", // Buttons, Badges, borders...
        300: "hsl(360, 82%, 89%)",
        100: "hsl(360, 100%, 97%)" // Notifications/labels background
      },
      yellow: {
        900: "hsl(43, 77%, 27%)",
        700: "hsl(43, 78%, 60%)", // hover, focus, selected effects
        500: "hsl(43, 89%, 70%)", // Buttons, Badges, borders...
        300: "hsl(45, 90%, 88%)",
        100: "hsl(45, 100%, 96%)" // Notifications/labels background
      }
    },
    social: {
      fb: "#29487d",
      ig: "#e95950",
      tw: "#55acee",
      in: "#007bb5",
      wu: "#4dc247"
    }
  },
  font: {
    family: {
        primary: '"Raleway", Open-sans, sans-serif',
        secondary: undefined,
        serif: '"Merriweather", serif;'
      }
  }
};
```

Since in this project we just need a couple of colors, I've translated the palette to this:

```
:root {
  --font-family-primary: "Nunito", sans-serif;
  --font-family-secondary: "Domine", serif;

  --primary-700: hsl(209, 91%, 46%);
  --primary-500: hsl(209, 100%, 50%);
  --primary-100: hsl(125, 65%, 93%);

  --grey-900: hsl(0, 0%, 23%);
  --grey-700: hsl(0, 0%, 38%);
  --grey-100: hsl(0, 0%, 97%);

  --accent-red-700: #af0900;
}
```

Where 100 is the lightest color and 900 is the darkest. It provides you the opportunity to add as much specification as you prefer.
You can or select:

- `300`, `500`, `700`
- `100`, `300`, `500`, `700`, `900`
- `100`, `200`, `300`, `400`, `500`, `600`, `700`, `800`, `900`

  Depending on how much detail you want.

### 🏞 Header Pattern

I chose using a pattern as `background-image` because I did not wanted a simple linear-gradient. It would make look the site too simple.

#### 🙅‍ Remove Gradient

Remove the class `Gradient` from the `<Header>` element. Do not forget to remove the class specification from the `index.css`

#### 💁‍ Change Gradient

For you information, I've used the https://www.heropatterns.com/ web application to generate my pattern because they look clean and awesome!

HeroPatterns it's and intuitive web app which can generate you patterns with the colors and patterns you indicate. It generates the `css` and it's ready to be pasted into your `.css` file.

### 📝 Manifest.json

The `manifest.json` is a file which is used for _Progressive Web Applications_. Its a way to provide _metadata_ from the file.
Remember to change the `short_name`, `name` and `colors`. If you need to include `icons` do it too!

It has a format like:

```
{
  "version": 1.0,
  "manifest_version": 1.0,
  "short_name": "CompanyName",
  "name": "CompanyName",
  "start_url": "index.html?launcher=true",
  "display": "standalone",
  "orientation": "portrait",
  "theme_color": "#0083ff",
  "background_color": "#0083ff",
  "icons": [
    {
      "src": "favicon.png",
      "sizes": "32x32",
      "type": "image/png"
    }
  ]
}
```

### 📬 Where to send the email you want to store

If you have this page, It means you want to store somehow email to send information later on. To do so, you'll have to update where to send those.

It's as easy as go to the `subscription.js` file and update the variable `storeEmailEndpoint`.
