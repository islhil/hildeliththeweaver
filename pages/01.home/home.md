---
title: 'Hildelith the Weaver'
images:
    -
        title: null
        thumbnail: 20250203_124147.jpg
        description: 'Tablet weave in plant dyed colours'
    -
        title: null
        thumbnail: 20241017_164740.jpg
        description: 'Nalbinding in the 2+2 stitch'
    -
        title: null
        thumbnail: IMG-20231107-WA0017.jpg
        description: 'Tablet weaving loom'
    -
        title: null
        thumbnail: IMG_20230728_105205_091.jpg
        description: 'Tablet weaving in practice'
    -
        title: null
        thumbnail: 20250108_113512.jpg
        description: 'Warp weighted loom in action'
    -
        title: null
        thumbnail: IMG_20230925_110509_558.jpg
        description: 'Tablet weave in practice'
    -
        title: null
        thumbnail: IMG-20240331-WA0039.jpg
        description: 'Preparing the tabby weave on the warp weighted loom'
    -
        title: null
        thumbnail: 20231217_121249.jpg
        description: 'Knee high nalbound socks'
form:
    action: /home
    name: contact-form
    fields:
        -
            name: name
            label: Name
            placeholder: Name
            type: text
            validate:
                required: true
        -
            name: email
            label: Email
            placeholder: Email
            type: email
            validate:
                required: true
        -
            name: message
            label: Message
            placeholder: Message
            type: textarea
            rows: 4
            validate:
                required: true
    buttons:
        -
            type: submit
            value: Send
            classes: special
        -
            type: reset
            value: Reset
    process:
        -
            email:
                from: '{{ config.plugins.email.from }}'
                to:
                    - '{{ config.plugins.email.from }}'
                subject: '[Contact] Message from {{ form.value.name|e }}'
                body: '{% include ''forms/data.html.twig'' %}'
        -
            save:
                fileprefix: contact-
                dateformat: Ymd-His-u
                extension: txt
                body: '{% include ''forms/data.txt.twig'' %}'
        -
            display: thank-you
---

