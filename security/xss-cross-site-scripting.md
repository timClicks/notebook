## Protecting iframes

If you're bringing in external content via an `<iframe>`, then you can inject CSP headers into it.
Browsers will support any policy that it more restrictive than what it contains:

```html
<iframe
  sandbox="allow-scripts"
  srcdoc="
    <meta
       http-equiv='Content-Security-Policy'
       content='default-src none; script-src unsafe-inline; style-src unsafe-inline;'>
          <!-- external content -->
    ">
</iframe>
```

Ensure that your external content has been passed through a parser, rather than being injected
by string concatenation, though. If you're relying on escaping any double quotes within the source,
you're in for a lot of pain.
