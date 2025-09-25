# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a personal Quarto extension for generating invoices using Typst format. It's based on [mcanouil/quarto-invoice](https://github.com/mcanouil/quarto-invoice) but customized with personal information and styling preferences.

## Extension Structure

- `_extension.yml` - Extension configuration file defining the Quarto extension
- `template.typ` - Main Typst template that calls partials
- `typst-template.typ` - Contains the invoice function and core formatting logic
- `typst-show.typ` - Template file that processes Quarto variables and passes them to Typst

## Key Components

### Template Files
- **template.typ**: Entry point that includes partials and body content
- **typst-template.typ**: Contains the `invoice()` function with parameters for sender, recipient, invoice details, formatting options
- **typst-show.typ**: Handles variable interpolation from Quarto YAML front matter to Typst function parameters

### Invoice Data Structure
The template expects YAML front matter with these sections:
- `sender`: Personal information (name, address, email, tax details)
- `recipient`: Client information (name, address)
- `invoice`: Invoice metadata (number, dates, references)
- `format`: Typst-specific formatting options
- `brand`: Typography and styling configuration

## Development Workflow

### Creating the Extension
When developing this as a proper Quarto extension that can be installed via `quarto add hubca25/quarto-invoice`:

1. Move template files from `example/_extensions/mcanouil/` to root `_extensions/hubca25/`
2. Update `_extension.yml` with personal branding and correct author information
3. Create template scaffold with pre-filled personal information
4. Test installation with `quarto add` command

### Testing Changes
1. Create a test document in a separate directory
2. Install the extension: `quarto add hubca25/quarto-invoice`
3. Render the document: `quarto render invoice.qmd`
4. Check the generated PDF output

### Template Customization
- Modify `typst-template.typ` for layout and styling changes
- Update default values in `typst-show.typ` for pre-filled personal information
- Adjust `_extension.yml` version and metadata when making changes

## Current Issues

The example directory shows a working invoice but the template structure isn't yet properly organized as a installable Quarto extension. The files need to be restructured to work with `quarto add` command.