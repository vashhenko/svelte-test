<nav>
    <div class="nav-container">
        <a href="/" class="nav-logo" title="Back to HomePage">Главная страница</a>
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
            title: 'Функции',
            href: '/about',
            isShow: true
        },
        {
            title: 'Статьи',
            href: '/blog',
            isShow: true
        },
        {
            title: 'Проекты',
            href: '/project',
            isShow: true
        },
        {
            title: 'Контакты',
            href: '/contact',
            isShow: false
        }
    ]
</script>

<style>
    .container {
        max-width: 1400px;
        margin: 50px auto;
    }
</style>
