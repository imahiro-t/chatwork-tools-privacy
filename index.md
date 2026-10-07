---
title: Chatwork Tools Privacy Policy
---

# Chatwork Tools Privacy Policy

Last updated: 2026-10-08

## Introduction

This privacy policy explains how the Chrome extension "Chatwork Tools" (the "extension") handles your data. The extension adds features to the Chatwork web app at `https://www.chatwork.com/` and `https://kcw.kddi.ne.jp/` (KDDI Chatwork), such as tag highlighting, inserting tags and custom messages, mentions, adding tasks, collapsing long messages, copying links and room IDs, and an optional AI writing assistant.

This policy covers only the extension. It does not cover Chatwork itself or the AI providers described below; their own privacy policies apply to them.

## Summary

- The extension does not send any data to servers operated by the developer. The developer does not collect, receive, or have access to your data.
- Your settings, including AI API keys, are stored in your own browser using Chrome's extension storage.
- The text in a Chatwork input field (message, file upload comment, or task) is sent to a third-party AI provider (Google Gemini, OpenAI, or Anthropic) only when you click an AI button that you have set up yourself next to that field, and only to the provider you chose, using your own API key.
- The extension does not sell your data, does not use it for advertising, analytics, or tracking, and does not use it for any purpose unrelated to the extension's features.

## Data stored on your device

### Settings (chrome.storage.sync)

The extension saves the settings you enter on its options page in Chrome's extension storage (`chrome.storage.sync`). These settings are:

- Custom messages (templates) for chat and tasks, with their labels, icons, and the room IDs they apply to.
- Task assignees that you register yourself: Chatwork account IDs, a label (such as a name), an icon, and the room IDs they apply to. The extension does not collect this information from Chatwork automatically; it stores only what you type in.
- The number of frequently used emoticons to show.
- AI button settings: label, icon, AI provider and model, prompt, and whether to use Chatwork formatting.
- AI API keys for Google Gemini, OpenAI, and Anthropic, if you enter them.
- Display and shortcut settings: collapsing long messages (on/off and number of lines), the help shortcut, and blurring My Chat for screen sharing.

This data stays in your browser. The developer cannot read it. Because the extension uses `chrome.storage.sync`, if you have turned on Chrome sync, Chrome syncs these settings to your other Chrome browsers signed in to the same Google account. That syncing is done by Chrome under Google's terms, not by the developer.

The settings export (JSON) on the options page does not include your AI API keys, and importing settings keeps the API keys you already have.

### Emoticon usage counts (localStorage)

To show your frequently used emoticons, the extension counts how many times you insert each emoticon and saves these counts in the browser's `localStorage` for the Chatwork site. The counts are not sent anywhere.

## Data sent to third-party AI providers

The AI writing assistant is optional. By default no AI button is shown, and if you do not set one up, no data is sent to any AI provider.

If you set up an AI button, the extension shows it next to each of these Chatwork input fields:

- the chat message input box,
- the comment box shown when you upload a file,
- the task input box in the "add task" dialog,
- the task input box in the "edit task" dialog.

If you also enter your own API key, then **only when you click an AI button**, the extension sends the following directly from your browser to the one AI provider you selected for that button:

- The entire text currently in the input field next to the button you clicked (nothing is sent if it is empty or contains only spaces). This is whatever the field contains at that moment, which may include text written by other people. For example, when you edit a task, the field already contains the existing task text, and when you turn a message into a task, Chatwork may fill the field with that message's text.
- The prompt you configured for the button, together with fixed instructions added by the extension (for example, a short guide to Chatwork tags and emoticons if you enabled formatting).
- The model name you selected.
- Your API key for that provider, which the provider requires to authenticate the request. For Google Gemini the key is sent as a URL query parameter; for OpenAI it is sent in the `Authorization` header; for Anthropic it is sent in the `x-api-key` header.

The text returned by the provider replaces the text in that input field, so you can review it before sending or saving. The extension does not store the text you sent or the response.

The providers the extension can send data to are:

- Google Gemini API (`generativelanguage.googleapis.com`) - [Google Privacy Policy](https://policies.google.com/privacy)
- OpenAI API (`api.openai.com`) - [OpenAI Privacy Policy](https://openai.com/policies/privacy-policy)
- Anthropic API (`api.anthropic.com`) - [Anthropic Privacy Policy](https://www.anthropic.com/legal/privacy)

Data you send to an AI provider is handled under that provider's terms and privacy policy and under your own account with that provider.

## Communication with Chatwork

- When you add a task with the extension, it sends your own Chatwork account ID, the room ID, the task content, the assignee account IDs, the deadline type, and the deadline to Chatwork's own server on the same site you are using (`/gateway/add_task.php`), using your existing Chatwork session in the page. This is the same kind of request the Chatwork web app makes itself. The extension does not store your Chatwork session.
- Profile images and emoticon images are loaded from Chatwork's servers (`appdata.chatwork.com` and `assets.chatwork.com`).
- Other features (tag highlighting, mentions, collapsing messages, blurring, help) work only within the Chatwork page in your browser and do not send data anywhere.

## Clipboard

When you use the copy features (message link, message text, room ID), the extension writes that text to your clipboard. The extension never reads your clipboard.

## What we do not do

- We do not send any data to servers operated by the developer, and we do not operate any such servers for the extension.
- We do not use analytics, advertising, or tracking tools, and we do not load remote code.
- We do not sell or transfer your data to third parties, except that the text described above is sent to the AI provider you choose when you click an AI button.
- We do not use or transfer your data for purposes unrelated to the extension's features.
- We do not use or transfer your data to determine creditworthiness or for lending purposes.

## Permissions and why they are needed

- `storage`: to save your settings (custom messages, task assignees, AI button settings and API keys, and display settings).
- `clipboardWrite`: to copy message links, message text, and room IDs to your clipboard.
- Host permissions for `https://generativelanguage.googleapis.com/*`, `https://api.openai.com/*`, and `https://api.anthropic.com/*`: to send the text of the input field to the AI provider you selected, only when you click an AI button.
- Content scripts on `https://www.chatwork.com/` and `https://kcw.kddi.ne.jp/`: to add the extension's features to the Chatwork page.

## Your choices and deleting your data

- You can change or delete your settings, including API keys, at any time on the extension's options page.
- If you do not want any text sent to AI providers, do not set up an AI button, or remove your AI buttons and API keys.
- Removing the extension from Chrome deletes the data it stored in Chrome's extension storage. If Chrome sync is on, Chrome also manages the synced copy.
- The emoticon usage counts are deleted when you clear the site data for the Chatwork site in your browser.

## Children's privacy

The extension is not directed to children and does not knowingly collect any personal information from children. The developer does not collect personal information from anyone.

## Changes to this policy

If the extension's handling of data changes, this page will be updated and the "Last updated" date above will be changed.

## Contact

If you have questions about this privacy policy, please open an issue at:
<https://github.com/imahiro-t/chatwork-tools-privacy/issues>
