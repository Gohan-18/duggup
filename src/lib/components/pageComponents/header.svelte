<script>
export {
    default
}
from './header.svelte';
import LogoIcon from '$lib/images/LogoIcon.png';
import LogoName from '$lib/images/38975_vector.png';
import HomeIcon from '$lib/images/Container.png';
import ExploreIcon from '$lib/images/ContainerExplore.png';
import LearnIcon from '$lib/images/ContainerLearn.png';
import PostIcon from '$lib/images/IconPost.png';
import ProfilPicture from '$lib/images/Frame 41ProfilPicture.png';
import DownArrow from '$lib/images/chevron-down.png';
import {
    Button
} from "$lib/components/ui/button/index.js";

import * as DropdownMenu from "$lib/components/ui/dropdown-menu";

let showStatusBar = true;
let showActivityBar = false;
let showPanel = false;

const data = {
    id: "1",
    label: "Krishna Kiran",
    link: ProfilPicture,
    email: "Kiran.Krishna@gmail.com"
};
</script>

<div class=" w-full fixed top-0 right-0 left-0 flex items-center justify-center h-16 bg-white z-50 " >
    <div class=" w-full h-full max-w-5xl border-b-2 border-zinc-300 border-dotted flex items-center justify-between " >
        <span class="flex items-center gap-1" >
            <img src={LogoIcon} alt="Logo" class="w-5 h-5" />
            <!-- <h1 class="text-sm text-zinc-700 font-bold ">duggup</h1> -->
            <img src={LogoName} alt="Logo Name" class="h-4 mt-0.5 " />
        </span>
        <span class="w-full flex items-center justify-end gap-4 " >
            <Button variant="outline" class="text-xs text-zinc-600 font-medium border-none flex items-center justify-center gap-1 " > <img src={HomeIcon} alt="Home Icon" class="w-5 h-5 mt-0.5" />Home</Button>
            <Button variant="outline" class="text-xs text-zinc-600 font-medium border-none flex items-center justify-center gap-1"> <img src={ExploreIcon} alt="Explore Icon" class="w-5 h-5 mt-0.5" />Explore</Button>
            <Button variant="outline" class="text-xs text-zinc-600 font-medium border-none flex items-center justify-center gap-1"> <img src={LearnIcon} alt="Learn Icon" class="w-5 h-5 mt-0.5" />Learn</Button>
            <Button variant="outline" class="text-xs text-zinc-600 font-medium  border-b-4 border-gray-600 flex items-center justify-center gap-3 px-6 "> <img src={PostIcon} alt="Post Icon" class="w-3 h-3 mt-0.5" /> Post</Button>
            <DropdownMenu.Root>
                <DropdownMenu.Trigger asChild let:builder>
                    <Button variant="outline" class="text-xs text-zinc-600 font-medium  border-none flex items-center justify-center gap-3 px-6 " builders={[builder]}> <img src={data?.link} alt="ProfilePicture" class="w-8 h-8 mt-0.5" /> {data?.label} <img src={DownArrow} alt="DownArrow" class="w-4 h-4 mt-0.5" /></Button>
                </DropdownMenu.Trigger>
                <DropdownMenu.Content class="w-56">
                    <DropdownMenu.Label>Menu</DropdownMenu.Label>
                    <DropdownMenu.Separator />
                    <DropdownMenu.CheckboxItem >
                        {data?.email}
                    </DropdownMenu.CheckboxItem>
                    <DropdownMenu.CheckboxItem bind:checked={showActivityBar}>
                        Log Out
                    </DropdownMenu.CheckboxItem>
                </DropdownMenu.Content>
            </DropdownMenu.Root>
        </span>
    </div>
</div>
