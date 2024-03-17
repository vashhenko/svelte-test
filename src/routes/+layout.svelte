<nav>
    <div class="nav-container">
        <a href="/" class="nav-logo" title="Back to HomePage">Вячеслав Чернышов</a>
        <div class="nav-links">
            {#each nav as link}
                {#if link.isShow}
                    <a href={link.href} class="link">{link.title}</a>
                {/if}
            {/each}
        </div>
    </div>
</nav>

<div class="container">
    <slot></slot>
</div>

<script>
    export let nav = [
        {
            title: 'Обо мне',
            href: '/about',
            isShow: true
        },
        {
            title: 'Блог',
            href: '/blog',
            isShow: true
        },
        {
            title: 'Портфолио',
            href: '/project',
            isShow: true
        },
        {
            title: 'Контакты',
            href: '/contact',
            isShow: true
        }
    ]
</script>

<style>
    .container {
        max-width: 1400px;
        margin: 50px auto;
    }
</style>
