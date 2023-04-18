<script>
    import { RichEditor, html, object} from 'svelte-rich-text';

    let startContent = [
        {
            type: 'h1',
            text: "Rich's favourite rich-text-editor",
        },
        {
            type: 'p',
            text: "This rich editor is different than most others, because in it's object representation it separates the text from the formatting.",
            format: [
                {
                    start: 20,
                    end: 29,
                    i: true,
                },
                {
                    start: 103,
                    end: 127,
                    b: true,
                },
            ],
        },
        {
            type: 'blockquote',
            text: 'It is aspiring to become the most minimalistic and most customizable rich-text-editor of all time.',
            format: [
                {
                    start: 29,
                    end: 46,
                    i: true,
                    b: true,
                },
            ],
        },
        {
            type: 'code',
            text: 'However, it still needs a lot of love to make it fully functional.',
        },
    ];
</script>

<RichEditor content={startContent} />

<br />
Object: <br />
<pre class="code">{JSON.stringify($object, null, 2)}</pre>

Html:<br />
<pre class="code">
    {$html}
</pre>

<style>
    :global(body) {
        font-family: sans-serif;
    }
    .code {
        background-color: #f5f5f5;
        border: 1px solid #ddd;
        border-radius: 4px;
        font-family: 'Courier New', Courier, monospace;
        font-size: 10px;
        line-height: 1.4;
        padding: 10px;
        white-space: pre-wrap;
    }
</style>
