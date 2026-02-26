# Oracle Code Assist Provider for Copilot

This extension registers [Oracle Code Assist]((https://www.oracle.com/application-development/code-assist/)) as a Copilot provider, enabling you to access and use Oracle Code Assist (OCA) models directly within VS Code Copilot Chat.

## Features

  * Integrates OCA models into Copilot Chat through a native VS Code chat provider.
  * Supports both OCA API styles: OpenAI-compatible Chat Completions and OpenAI Responses API.
  * Automatically discovers available models.
  * Supports two access modes: `internal` (Oracle employee) and `external` (non-Oracle employee).

## Requirements

  * VS Code `1.104.0` or newer
  * GitHub Copilot Chat extension installed (`github.copilot-chat`)
  * Network access to Oracle identity and OCA API endpoints
  * An account entitled to use Oracle Code Assist

## Installation and Configuration

  1. Install the extension from the VS Code Marketplace.
  2. Ensure GitHub Copilot Chat is installed and enabled.
  3. Open Copilot Chat → model picker → `Manage Models`
  4. On first use, complete sign-in in your browser.
  5. Enable models under `Oracle Code Assist`.

## Extension Settings

This extension contributes:

  + `ocacopilot.mode`
    * Type: `string`
    * Allowed: 
      - `internal`: Oracle employee account
      - `external`:  non-Oracle employee account
    * Default: `internal`
    * Meaning: selects which Oracle identity and OCA endpoint configuration is used.

## How it works

  * This extension registers an LM chat provider in VS Code.
  * It routes chat requests to Oracle Code Assist endpoints using your authenticated Oracle identity.

## Privacy and Security

  * Token storage location: VS Code Secret Storage.
  * Data sent: chat prompts/context are sent to configured Oracle Code Assist endpoints for inference.

## Troubleshooting

### No models appear

  * Verify your account has OCA entitlement.
  * Confirm `ocacopilot.mode` matches your account type.
