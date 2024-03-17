<script>
    export let name;
        const icons = [
    {
        box: 24,
        name: 'check-mark',
        svg: '<path d="M8.5 15.9l-3.4-3.4-1 1 4.4 4.4 8.5-8.5-.9-1z"></path>',
    },
    { 
        box: 32,  
        name: 'delete',
        svg: '<path d="M12 12h2v12h-2z" /><path d="M18 12h2v12h-2z" /><path d="M4 6v2h2v20a2 2 0 0 0 2 2h16a2 2 0 0 0 2-2V8h2V6zm4 22V8h16v20z" /><path d="M12 2h8v2h-8z" />',
    },
    ];
        let icon = icons.find((item) => item.name == name);
</script>
    <svg
        class={$$props.class}
        viewBox="0 0 {icon.box} {icon.box}">
        {@html icon.svg}
    </svg>