# NG Alert

A lightweight, accessible, zero-dependency global alert dialog library for any website or web app.

- **Zero dependencies** — pure vanilla JavaScript
- **Accessible** — `role="alertdialog"`, `aria-labelledby`, `aria-describedby`, focus management, keyboard dismiss
- **4 types** — `success`, `error`, `warning`, `info`
- **Auto-dismiss** with animated progress bar
- **Customizable** — duration, labels, overlay/ESC close behavior
- **~4 KB** total (JS + CSS)

---

## Installation

### CDN (easiest)

```html
<link rel="stylesheet" href="https://YOUR_DOMAIN/ngalert/dist/ngalert.css">
<script src="https://YOUR_DOMAIN/ngalert/dist/ngalert.js"></script>
```

## Quick Start

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <link rel="stylesheet" href="dist/ngalert.css">
</head>
<body>
  <button onclick="NGAlert.success('Your file was saved!')">Show Alert</button>
  <script src="dist/ngalert.js"></script>
</body>
</html>
```

---

## Usage

### Shorthand methods

```js
NGAlert.success('Your changes have been saved.');
NGAlert.error('Something went wrong. Please try again.');
NGAlert.warning('Your session is about to expire.');
NGAlert.info('A new version is available.');
```

### With custom title and options

```js
NGAlert.success('Invoice #1042 has been sent.', {
  title: 'Email Sent',
  duration: 4000
});
```

### Generic `show()`

```js
NGAlert.show('Message text', 'success', { title: 'Done', duration: 3000 });
```

### Dismiss programmatically

```js
const alert = NGAlert.info('Loading…', { duration: 0 }); // duration:0 stays open
// later...
alert.dismiss();
// or dismiss whatever is currently shown:
NGAlert.dismiss();
```

---

## Options

| Option | Type | Default | Description |
|---|---|---|---|
| `title` | `string` | type label | Title shown in the alert |
| `duration` | `number` | `5000` | Auto-dismiss delay in ms. Use `0` to disable |
| `closeOnOverlay` | `boolean` | `true` | Click backdrop to close |
| `closeOnEsc` | `boolean` | `true` | Press Escape to close |

---

## Global Config

Set defaults once at app startup:

```js
NGAlert.init({
  duration: 4000,
  closeOnOverlay: false,
  labels: {
    success: 'Done',
    error: 'Oops',
    warning: 'Heads Up',
    info: 'FYI'
  }
});
```

---

## Return Value

Every `show()` / shorthand call returns an instance object:

```js
const instance = NGAlert.success('Hello!');
instance.dismiss();    // close it early
instance.element;      // the root DOM element
```

---

## CSS Custom Properties

Override these in your own CSS to theme the library:

```css
:root {
  --nga-z-index:       9999;
  --nga-overlay:       rgba(13, 17, 23, 0.36);
  --nga-radius:        16px;
  --nga-shadow:        0 24px 56px rgba(2, 8, 23, 0.22);
  --nga-success:       #10b981;
  --nga-error:         #ef4444;
  --nga-warning:       #f59e0b;
  --nga-info:          #0ea5e9;
  --nga-bg-success:    #eefaf6;
  --nga-bg-error:      #ffeded;
  --nga-bg-warning:    #fff9ed;
  --nga-bg-info:       #e8f6ff;
  --nga-panel-text:    #1f2937;
  --nga-panel-subtext: #4b5563;
}
```

---

## API Reference

```js
NGAlert.version          // "0.1.0"
NGAlert.init(config)     // set global defaults
NGAlert.show(msg, type, options)
NGAlert.success(msg, options)
NGAlert.error(msg, options)
NGAlert.warning(msg, options)
NGAlert.info(msg, options)
NGAlert.dismiss()        // dismiss the current alert
```

Both `NGAlert` and `ngAlert` are available as global variables.

---

## Browser Support

All modern browsers (Chrome, Firefox, Safari, Edge). No IE11 support.

---

## License

[MIT](LICENSE)

---

# NG Alert (ភាសាខ្មែរ)

បណ្ណាល័យ Alert Dialog សកលដែលស្រាល ប្រើបានងាយ ស្របតាមស្តង់ដារ Accessibility ហើយមិនពឹងផ្អែកលើ dependency ណាមួយ សម្រាប់គេហទំព័រ ឬ web app គ្រប់ប្រភេទ។

- **មិនមាន dependencies** — JavaScript សុទ្ធ (vanilla JS)
- **គាំទ្រ Accessibility** — `role="alertdialog"`, `aria-labelledby`, `aria-describedby`, ការគ្រប់គ្រង focus និងការបិទតាម keyboard
- **មាន 4 ប្រភេទ** — `success`, `error`, `warning`, `info`
- **បិទដោយស្វ័យប្រវត្តិ** ជាមួយ progress bar មាន animation
- **អាចកំណត់តាមបំណងបាន** — រយៈពេល, label, ការបិទតាម overlay/ESC
- **ប្រហែល ~4 KB** សរុប (JS + CSS)

---

## ការដំឡើង

### CDN (ងាយស្រួលបំផុត)

```html
<link rel="stylesheet" href="https://YOUR_DOMAIN/ngalert/dist/ngalert.css">
<script src="https://YOUR_DOMAIN/ngalert/dist/ngalert.js"></script>
```

## ចាប់ផ្តើមប្រើរហ័ស

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <link rel="stylesheet" href="dist/ngalert.css">
</head>
<body>
  <button onclick="NGAlert.success('Your file was saved!')">Show Alert</button>
  <script src="dist/ngalert.js"></script>
</body>
</html>
```

---

## របៀបប្រើ

### មុខងារ shorthand

```js
NGAlert.success('ការកែប្រែរបស់អ្នកត្រូវបានរក្សាទុករួចរាល់។');
NGAlert.error('មានបញ្ហាកើតឡើង។ សូមព្យាយាមម្តងទៀត។');
NGAlert.warning('សម័យចូលប្រើរបស់អ្នកជិតផុតកំណត់ហើយ។');
NGAlert.info('មានកំណែថ្មីអាចធ្វើបច្ចុប្បន្នភាពបាន។');
```

### ប្រើជាមួយចំណងជើង និង options ផ្ទាល់ខ្លួន

```js
NGAlert.success('វិក្កយបត្រ #1042 ត្រូវបានផ្ញើរួចហើយ។', {
  title: 'ផ្ញើអ៊ីមែលរួចរាល់',
  duration: 4000
});
```

### ប្រើ `show()` ទូទៅ

```js
NGAlert.show('អត្ថបទសារ', 'success', { title: 'រួចរាល់', duration: 3000 });
```

### បិទដោយកម្មវិធី

```js
const alert = NGAlert.info('កំពុងដំណើរការ…', { duration: 0 }); // duration:0 នឹងបង្ហាញរហូត
// later...
alert.dismiss();
// ឬបិទសារដែលកំពុងបង្ហាញបច្ចុប្បន្ន:
NGAlert.dismiss();
```

---

## ជម្រើស (Options)

| Option | Type | Default | ពិពណ៌នា |
|---|---|---|---|
| `title` | `string` | type label | ចំណងជើងដែលបង្ហាញក្នុង alert |
| `duration` | `number` | `5000` | ពេលវេលាបិទស្វ័យប្រវត្តិ (ms)។ ប្រើ `0` ដើម្បីបិទមុខងារនេះ |
| `closeOnOverlay` | `boolean` | `true` | ចុច backdrop/overlay ដើម្បីបិទ |
| `closeOnEsc` | `boolean` | `true` | ចុចគ្រាប់ចុច Escape ដើម្បីបិទ |

---

## ការកំណត់សកល

កំណត់ default ម្តងនៅពេល app ចាប់ផ្តើម:

```js
NGAlert.init({
  duration: 4000,
  closeOnOverlay: false,
  labels: {
    success: 'រួចរាល់',
    error: 'អូ៎!',
    warning: 'សូមប្រុងប្រយ័ត្ន',
    info: 'ព័ត៌មាន'
  }
});
```

---

## តម្លៃត្រឡប់

ការហៅ `show()` / shorthand នីមួយៗ នឹងត្រឡប់ object instance មួយ:

```js
const instance = NGAlert.success('សួស្តី!');
instance.dismiss();    // បិទមុនពេលកំណត់
instance.element;      // root DOM element
```

---

## CSS Custom Properties

អ្នកអាច override តម្លៃខាងក្រោមនៅក្នុង CSS របស់អ្នក ដើម្បីប្តូរ theme បាន:

```css
:root {
  --nga-z-index:       9999;
  --nga-overlay:       rgba(13, 17, 23, 0.36);
  --nga-radius:        16px;
  --nga-shadow:        0 24px 56px rgba(2, 8, 23, 0.22);
  --nga-success:       #10b981;
  --nga-error:         #ef4444;
  --nga-warning:       #f59e0b;
  --nga-info:          #0ea5e9;
  --nga-bg-success:    #eefaf6;
  --nga-bg-error:      #ffeded;
  --nga-bg-warning:    #fff9ed;
  --nga-bg-info:       #e8f6ff;
  --nga-panel-text:    #1f2937;
  --nga-panel-subtext: #4b5563;
}
```

---

## ឯកសារយោង API

```js
NGAlert.version          // "0.1.0"
NGAlert.init(config)     // កំណត់ default សកល
NGAlert.show(msg, type, options)
NGAlert.success(msg, options)
NGAlert.error(msg, options)
NGAlert.warning(msg, options)
NGAlert.info(msg, options)
NGAlert.dismiss()        // បិទ alert ដែលកំពុងបង្ហាញ
```

ទាំង `NGAlert` និង `ngAlert` អាចប្រើបានជា global variables។

---

## Browser ដែលគាំទ្រ

Browser ទំនើបទាំងអស់ (Chrome, Firefox, Safari, Edge)។ មិនគាំទ្រ IE11 ទេ។

---

## អាជ្ញាប័ណ្ណ

[MIT](LICENSE)
