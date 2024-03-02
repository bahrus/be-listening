# be-listening

*be-listening* specializes in one scenario supported by be-linked:

Instead of:

```html
<my-light-weight-container>
    <number-generator></number-generator>
    <metric-units enh-be-linked='
        On value changed event of previous element sibling pass value property to cm property of $0
        where we enable debugging
        and we fire changed event
        and we nudge previous element
        and we skip initialization. 
    '></metric-units>
</my-light-weight-container
```

we can do:

```html
<my-light-weight-container>
    <number-generator></number-generator>
    <metric-units 
        enh-be-listening='to number generator for value changed event and copy value to property cm.'
        enh-be-listening-config='{
            "skipInitialization": true,
            "nudge": true,
            "fire": "change"
        }'
    >
    </metric-units>
</my-light-weight-container
```

