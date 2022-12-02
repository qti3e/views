<script>
	import '../app.css';
	import { Footer, FooterCopyright, FooterLinkGroup, FooterLink } from 'flowbite-svelte';
    import { Navbar, NavBrand, NavLi, NavUl, NavHamburger, Avatar, Dropdown, DropdownItem, DropdownHeader, DropdownDivider } from 'flowbite-svelte'
	import { DarkMode } from 'flowbite-svelte';
</script>

<Navbar let:hidden let:toggle>
    <NavBrand href="/">
        <img src="https://flowbite.com/docs/images/logo.svg" class="mr-3 h-6 sm:h-9" alt="Flowbite Logo"/>
        <span class="self-center whitespace-nowrap text-xl font-semibold dark:text-white">Flowbite</span>
    </NavBrand>
    <div class="flex items-center md:order-2">
        <Avatar id="avatar-menu" src="/images/profile-picture-3.webp" />
        <NavHamburger on:click={toggle} class1="w-full md:flex md:w-auto md:order-1"/>
    </div>
    <Dropdown placement="bottom" triggeredBy="#avatar-menu">
        <DropdownHeader>
        <span class="block text-sm"> Bonnie Green </span>
        <span class="block truncate text-sm font-medium"> name@flowbite.com </span>
        </DropdownHeader>
        <DropdownItem>Dashboard</DropdownItem>
        <DropdownItem>Settings</DropdownItem>
        <DropdownItem>Earnings</DropdownItem>
        <DropdownDivider />
        <DropdownItem>Sign out</DropdownItem>
    </Dropdown>
    <NavUl {hidden}>
        <NavLi href="/" active={true}>Home</NavLi>
        <NavLi href="/about">About</NavLi>
        <NavLi href="/services">Services</NavLi>
        <NavLi href="/pricing">Pricing</NavLi>
        <NavLi href="/contact">Contact</NavLi>
    </NavUl>
    </Navbar>

<article>
    <slot />
</article>

<Footer>
    <FooterCopyright href="/" by="Parsa™" year={2022} />
    <FooterLinkGroup
        ulClass="flex flex-wrap items-center mt-3 text-sm text-gray-500 dark:text-gray-400 sm:mt-0"
    >
        <FooterLink href="/">About</FooterLink>
        <FooterLink href="/">Privacy Policy</FooterLink>
        <!-- <FooterLink href="/">Licensing</FooterLink> -->
        <FooterLink href="/">Contact</FooterLink>
    </FooterLinkGroup>
    <DarkMode btnClass='text-gray-500 dark:text-gray-400 hover:bg-gray-100 dark:hover:bg-gray-700 focus:outline-none focus:ring-4 focus:ring-gray-200 dark:focus:ring-gray-700 rounded-lg text-lg p-2.5 z-50' />
</Footer>