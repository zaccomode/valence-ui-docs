---
description: 'Last updated: 4.0.0'
---

# Generic input props

## Generic input props

_Extends `GenericLayoutProps`, accepts a type input `T = string`._

<table data-full-width="true"><thead><tr><th width="145">Property</th><th width="302">Type</th><th>Description</th></tr></thead><tbody><tr><td>value</td><td><code>T</code></td><td>The value of this input. Use this in conjunction with <code>onInput</code> or <code>onChange</code> to create controlled inputs.</td></tr><tr><td>setValue</td><td><code>(value: T) => void</code></td><td>Sets the value of this input. Use this in conjunction with <code>value</code> to create controlled inputs.</td></tr><tr><td>size</td><td><code>ComponentSize</code></td><td>This input's size class. Defaults to theme default.</td></tr><tr><td>radius</td><td><code>ComponentSize</code></td><td>This input's radius size class. Defaults to theme default.</td></tr><tr><td>disabled</td><td><code>boolean</code></td><td>Whether this input is disabled.</td></tr><tr><td>readOnly</td><td><code>boolean</code></td><td>Whether this input is readonly.</td></tr><tr><td>required</td><td><code>boolean</code></td><td>Whether this input is required.</td></tr><tr><td>autoFocus</td><td><code>boolean</code></td><td>Whether to focus this input on mount.</td></tr><tr><td>loading</td><td><code>boolean</code></td><td>Whether this input is loading.</td></tr><tr><td>form</td><td><code>string</code></td><td>Associates this input with a form element.</td></tr><tr><td>name</td><td><code>string</code></td><td>The name of this input. Submitted with the form as part of a name/value pair.</td></tr></tbody></table>

## Generic text input props

_Extends `GenericInputProps<string>`._

<table><thead><tr><th width="148">Property</th><th width="169">Type</th><th>Description</th></tr></thead><tbody><tr><td>icon</td><td><code>ReactNode</code></td><td>An icon to display at the left side of this input.</td></tr><tr><td>placeholder</td><td><code>string</code></td><td>Text that appears in this input when it has no value.</td></tr><tr><td>minLength</td><td><code>number</code></td><td>The minimum length of this input's <code>value</code>.</td></tr><tr><td>maxLength</td><td><code>number</code></td><td>The maximum length of this input's <code>value</code>.</td></tr><tr><td>pattern</td><td><code>string</code></td><td>A regex pattern to use for validation.</td></tr><tr><td>material</td><td><a href="../../core-concepts/materials/README.md"><code>Material</code></a></td><td>This input's material. Defaults to <code>theme.materials.input</code>.</td></tr><tr><td>inputStyle</td><td><code>CSSProperties</code></td><td>Optional styles to apply to the input component.</td></tr></tbody></table>

## Generic text input event props

Extends `MouseClickEvents`, `MouseEvents`, `PointerEvents`, `FocusEvents`, `KeyboardEvents`.

<table><thead><tr><th width="153">Property</th><th width="277">Type</th><th>Description</th></tr></thead><tbody><tr><td>onInput</td><td><code>(event: React.FormEvent) => void</code></td><td>Fires when the value of this input has been changed.</td></tr><tr><td>onChange</td><td><code>(event: React.FormEvent) => void</code></td><td>Fires when the value of this input has been changed. This is functionally the same as <code>onInput</code> because of how React handles these events.</td></tr><tr><td>onInvalid</td><td><code>(event: React.FormEvent) => void</code></td><td>Fires when the input's value does not satisfy its validation constraints.</td></tr><tr><td>onEnterPress</td><td><code>(event: React.FormEvent) => void</code></td><td>Fires when the <code>enter</code> key is pressed.</td></tr></tbody></table>

## Changelog

* **4.0.0:** Removed `variant` from `GenericInputProps`; `GenericTextInputProps` gained `material`. `setValue` is now typed `(value: T) => void` rather than a React state setter.
