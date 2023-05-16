# JSON Resume

My CV in JSON format based on <https://jsonresume.org/>.

![Preview of resume online](images/resume_preview.png)

## Where does it end up?

1. On [`cv.alifeee.co.uk`]
1. On the [json-resume registry] (via the [gist])
1. PDF on the [releases page] or [website]

[`cv.alifeee.co.uk`]: https://alifeee.github.io/json-resume/
[json-resume registry]: https://registry.jsonresume.org/alifeee
[gist]: https://gist.github.com/alifeee/97f9ac1642b1c46cf66942c3f079a42f
[releases page]: https://github.com/alifeee/json-resume/releases
[website]: https://alifeee.github.io/json-resume/Alfred-Renn-CV.pdf

## Changing the theme

A list of themes can be found at [https://jsonresume.org/themes/](https://jsonresume.org/themes/). A lot of these are broken. Some themes that look nice, and work well on mobile are:

| Theme | Works locally | Works on registry |
| ----- | -------------- | ----------------- |
| [Even](https://github.com/rbardini/jsonresume-theme-even) | ✅ | ❌ |
| [Kendall](https://github.com/linuxbozo/jsonresume-theme-kendall) | ✅ | ✅ |
| [Paper](https://github.com/TimDaub/jsonresume-theme-paper) | ✅ | ❌ |
| [Eloquent](https://github.com/thibaudcolas/jsonresume-theme-eloquent) | ✅ | ❌ |
[Elegant](https://registry.jsonresume.org/alifeee?theme=elegant) | ❌² | ✅ |
| [OnePage](https://github.com/ainsleyc/jsonresume-theme-onepage) | ❌² | ✅ |

² - not installed locally as very outdated and full of npm vulnerabilities

### Changing theme remotely

The easiest way to experiment with themes is to update the resume gist (push to main) and visit the [JSON resume registry](https://registry.jsonresume.org/alifeee). The theme can be changed via the `theme` query parameter, e.g.:

```url
https://registry.jsonresume.org/alifeee?theme=even
```

### Changing theme locally

Alternatively, the theme can be changed locally - see [development](#development).

## Development

### Prerequisites

| Requirement | Version |
| ----------- | ------- |
| Node        | 19.8.1  |
| npm         | 9.5.1   |

### Install dependencies

```bash
npm install
```

### Validate JSON

```bash
npm run test
```

### Build HTML

```bash
npm run build-html
```

### Build HTML with theme "even"

```bash
npm install jsonresume-theme-even
npm run build-html -- even
```

### Run with watch

```bash
npm run dev
```

Open `resume.html` using the VSCode Live Server extension.

![Context menu for live server in VSCode](images/live%20server.png)

### Build PDF

```bash
npm run build-pdf
```

## GitHub Actions

See [the files themselves](.github/workflows) for more details.

| Action | Description |
| ------ | ----------- |
| [`test.yml`] | Runs on pull request and push to `main`. Verifies that the `resume.json` conforms to the [json-resume schema] |
| [`publish.yml`] | Runs on release (or tag). Builds the HTML and PDF, then pushes to: [releases page]; `publish` branch (viewable on [my GitHub pages]); and [resume gist]. |

[`test.yml`]: .github/workflows/test.yml
[json-resume schema]: https://jsonresume.org/schema/
[`publish.yml`]: .github/workflows/publish.yml
[resume gist]: https://gist.github.com/alifeee/97f9ac1642b1c46cf66942c3f079a42f
[my GitHub pages]: https://alifeee.github.io/json-resume/
