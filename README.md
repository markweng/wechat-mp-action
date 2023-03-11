# WeChat MiniProgram GitHub Action

A [GitHub Action](https://github.com/features/actions) to automate deploying WeChat MiniProgram by using [miniprogram-ci](https://www.npmjs.com/package/miniprogram-ci).

It will enable workflows to easily preview and upload your MiniProgram to the WeChat.

The implementation of preview or upload is the same as VSCode extension [miniprogram-vscode-extension](https://marketplace.visualstudio.com/items?itemName=crazyurus.miniprogram-vscode-extension).

# Usage

Here's an example workflow which publishes an extension when you push to the master branch.

## Input

| Name | Required | Description | Default Value |
| :----: | :----: | :---- | :----: |
| action_type | `false` | Action type, preview or upload | `upload` |
| project_path | `false` | Project path, which contains project.config.json | `.` |
| page_path | `false` | Page path, one of the pages in app.json |  |
| page_query | `false` | Page query |  |
| scene | `false` | Scene code | `1011` |
| version | `false` | Publish version | `1.0.0` |
| description | `false` | Release notes |  |

## Output

| Name | Always | Description | Default Value |
| :----: | :----: | :---- | :----: |
| preview_qrcode | `false` | The base64 content of the MiniProgram to preview the QR code |  |
| preview_qrcode_path | `false` | The file path of the MiniProgram to preview the QR code |  |

# Secrets

The `PRIVATE_KEY` secret is used to authenticate with WeChat when running the `miniprogram-ci` CLI. You can find out how to create this token here on the WeChat Developers: [CI](https://developers.weixin.qq.com/miniprogram/dev/devtools/ci.html)
# Example Use Cases

- Preview MiniProgram if the `master` branch has changed since the last build.
- Upload MiniProgram when the tag is created on GitHub.

Here is a example project [recruit-miniprogram](https://github.com/crazyurus/recruit-miniprogram/tree/master/.github/workflows)
