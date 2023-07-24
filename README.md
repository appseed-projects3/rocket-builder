# [Free Website Builder](https://www.simpllo.com/)

**Free & [Open-Source Site Builder](https://www.simpllo.com/)** that uses `Vanilla JS` and a `Remote Server` for components injection - Actively supported by `AppSeed`.

- 👉 [Simpllo Builder](https://www.simpllo.com/) - `Live DEMO`
- 🚀 [Join the Community](https://discord.gg/AWh6TFcEwU) - `Discord`
- 🫶 `Become a Sponsor` - **[PAY $9](https://appseed.gumroad.com/l/free-site-builder)** (`One-Time-Payment` via GUMROAD)

<br />

![Free & Open-Source Website Builder - Actively Supported by AppSeed.](https://github.com/appseed-projects3/rocket-builder/assets/108474994/c756f23d-1191-43d2-bb1b-8e223714a6c6)

<br />

## Roadmap & [SPECS](https://docs.google.com/document/d/1YbmZro0b8ucMGE227xSMzcQGNbWgTaiOKfjgEW9RsWE/edit?usp=sharing) 

| Status | Item | info | 
| --- | --- | --- |
| ✅ | **Core** |  `Vanilla JS` |
| ✅ | **Components** | `Bootstrap 5` |
| ✅ | **Remote Components Server** | https://components-server.onrender.com/kits/bs5/ |
| ✅ | **Persistence** (local storage) | Save, Restore, Clear |
| ✅ | **One-Page Layout** | `Single Component` Drag & Drop |
| ✅ | **Component Customization** | Text-Only |
| ✅ | **Grid Components** | This allows to inject predefined rows (2,3,4 columns) |
| ✅ | **USE Remote Components** | `Yes` |
| ✅ | **Component Customization** | Texts, Links |
| ✅ | **Component Customization** | Images |
| ✅ | **Component Styling** | CSS, Classes |
| ✅ | **PAGE Customization** | CSS |
| ✅ | **PAGE Customization** | JS |
| ✅ | **Manage SEO** | Title, Description, Keywords |
| ✅ | **Handle Multiple Pages** | YES |

<br />

## `Compile the Builder`

> Tested with `Node 16.x, 18.x`.
 
```bash
$ git clone https://github.com/app-generator/rocket-builder.git
$ cd rocket-builder/builder
$ yarn
$ yarn dev    # development (LIVE Reload)
$ yarn build  # production  (dist FOLDER)
```

<br />

## Components `Server` (distant)

> Managed by `Flask` (optional). By default, a **[LIVE Components Server](https://components-server.onrender.com/kits/)** is used.

```bash
$ cd rocket-builder/backend
$
$ virtualenv env
$ # Or
$ python -m venv env 
$
$ source env/bin/activate  # Linux
$ # Or
$ .\env\Scripts\activate   # Windows
$
$ pip install -r requirements.txt
$ flask run --debug
```

Here is the output:

- `http://localhost:5000/`
- `http://localhost:5000/kits/`, returns available KITS
  - 'material-kit'
  - 'kit2'
- `http://localhost:5000/kits/material-kit/`, return `Material Kit` assets

```json
{
    "name": "Material Kit BS5 ",
    "version": "0.0.0",
    "type": "kit",
    "material-kit": {
        "layouts": "base.html",
        "components": {
            "footers": {
                "footer.html": "NA"
            },
            "headers": {
                "header.html": "NA"
            },
            "navigation": {
                "navigation.html": "NA"
            },
            "general": {
                "section1.html": "NA"
            }
        }
    }
}
```

<br />

## Add new component

- Navigate to `backend/apps/templates/bs5/components`
- create the component like `footer.html`
- Edit the file and add the HTML code
- Compute the `Base64` hash using service:
  - https://www.base64encode.org/
- Update `info.json` and add the new component using existing category or a new one
  - Syntax:

```json
... (truncated) ...
        "components": {
            "footer": {
                "footer.html": "BASE64_Hash HERE"
            }, 
        }   
... (truncated) ...         
```

> NOTE: The UI Builder uses the `local storage` to cache the `info.json` pulled from the server.

In order to have the latest version, please open an incognito window or clean manually the data from the local storage.

<br />

## [License EULA ](./LICENSE.md)

For more information regarding `licensing`, please contact [AppSeed](http://appseed.us/), < *support@appseed.us* >.

<br />

---
[Free Site Builder](https://www.simpllo.com/) - Provided by **AppSeed**.
