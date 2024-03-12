<script>
export {
    default
}
from './main.svelte';

import ProfilPicture from '$lib/images/Frame 41ProfilPicture.png';
import LogoIcon from '$lib/images/LogoIcon.png';
import LogoIconBetterUp from '$lib/images/SocialIconsBetterup.png';
import SendIcon from '$lib/images/IconSendImg.png';
import JeffBezos from '$lib/images/Rectangle 71JeffBezos.png';
import Laptop from '$lib/images/Rectangle 71Laptop.png';
import SamAltman from '$lib/images/Image FrameSamAltman.png';
import RandomImg from '$lib/images/Rectangle 71Random (1).png';
import Button from '../ui/button/button.svelte';
import * as Card from "$lib/components/ui/card";

const data = {
    profilePicture: ProfilPicture,
    userName: "Krishna Kiran",
    about: "Co-Founder and CEO at Duggup - Social network for people in tech. Ex-Amazon Head of Engineering. I write hot-takes on building a business, shipping delightful products and accelerating product and career growth.",
    companyIcon: LogoIcon,
    compsnyName: "Duggup",
    title: "Co-Founder & CEO",
    websiteLink: "Link"
}

const handleArticleCardClick = () => {
    alert("This will open the clicked article!!")
}

const contentData = [{
        title: "No amount of technology can convert a bad story into a good story.",
        poster: JeffBezos,
        id: 1
    },
    {
        title: "Most people don't have original ideas. Here is how Sam Altman pushes himself to have unpopular ideas.",
        poster: SamAltman,
        id: 2
    },
    // {
    //     role: "Co-Founder and CEO",
    //     type: "Full Time",
    //     location: "Remote",
    //     jobUpdate: true,
    //     poster: "",
    //     id: 3
    // },
    {
        title: "Startup Lesson I am reflecting. Don't build for the 'average person'.",
        poster: Laptop,
        id: 4
    },
    {
        title: "Your biggest regrets at 80 will be acts of omission.",
        poster: RandomImg,
        id: 5
    },
]

const careerUpdates = [{
        id: 1,
        companyName: "Duggup",
        companyLogo: LogoIcon,
        companyLocation: "San Francisco Bay Area",
        joiningDate: "Nov 2023"
    },
    {
        id: 2,
        companyName: "BetterUp",
        companyLogo: LogoIconBetterUp,
        companyLocation: "San Francisco Bay Area",
        joiningDate: "Sep 2022"
    },
]
</script>

<div class="flex items-center justify-start flex-col pb-20 " >
    <div class="w-full h-full max-w-3xl flex items-center justify-between pb-10 ">
        <span class="w-1/4" >
            <img src={data?.profilePicture} alt="Logo" class="w-24 h-24" />
            <h2 class="text-md text-zinc-600 font-bold ">{data?.userName}</h2>
        </span>
        <span class="w-2/4 " >
            <p class="text-xs text-zinc-500 font-medium mb-3">{data?.about}</p>
            <Button on:click={() => alert("This is to show if following the user or not!!")} size="sm" variant="outline" class="text-xs  text-zinc-600 font-medium h-8 border-b-4 border-gray-600 flex items-center justify-center gap-3 px-6 ">Followed</Button>
        </span>
        <span class="w-1/4 h-full flex flex-col items-end justify-start gap-1" >
            <img src={data?.companyIcon} alt="Logo" class="w-6 h-6 rounded-full" />
            <span class="flex flex-col items-end justify-end" >
                <h3 class="text-xs text-zinc-700 font-bold ">{data?.compsnyName}</h3>
                <p class="text-xxs text-gray-400 font-semibold ">{data?.title}</p>
            </span>
            <span class="flex items-center justify-center gap-1 " >
                <a href={data?.websiteLink} class="text-xxs text-zinc-500 font-medium  hover:underline">My Website</a>
                <img src={SendIcon} alt="SendLogo" class="w-2 h-2" />
            </span>
        </span>
    </div>
    <div class="flex items-start justify-start" >

        <div class="w-1/6 flex flex-col gap-14 items-end pr-10 " >
            {#each careerUpdates as careerUpdate (careerUpdate?.id)}
            <span class=" flex items-end flex-col relative " >
                <!-- <span class=" absolute h-10 rounded-full border-2 border-dotted border-blue-500  " /> -->
                <img src={careerUpdate?.companyLogo} alt="Logo" class="w-8 h-8 rounded-full mb-1" />
                <h3 class="text-xs text-gray-700 font-bold ">{careerUpdate?.companyName}</h3>
                <p class="text-xxs text-gray-400 font-semibold ">{careerUpdate?.companyLocation}</p>
                <p class="text-xxs text-gray-400 font-semibold ">Joined</p>
                <p class="text-xxs text-gray-400 font-semibold ">{careerUpdate?.joiningDate}</p>
            </span>
            {/each}
        </div>

        <div class=" border-l-2 border-dotted border-blue-500 w-5/6 py-5 " >
            <div class="grid grid-cols-2 gap-4 pl-10 pr-10 " >
                {#each contentData as data (data?.id)}
                <div  class="relative" on:click={handleArticleCardClick} >
                    <Card.Root class="cursor-pointer  " >
                        <!-- <span class=" absolute w-5 h-5 rounded-full border-2   " /> -->
                        <Card.Header>
                            <img src={data?.poster} alt="Logo" class="rounded-t-xl " />
                            <!-- <Card.Title>Card Title</Card.Title>
                            <Card.Description>Card Description</Card.Description> -->
                        </Card.Header>
                        <Card.Content>
                            <p class="text-sm text-zinc-700 font-medium line-clamp-2 w-full " >{data?.title}</p>
                        </Card.Content>
                        <!-- <Card.Footer>
                          <p>Card Footer</p>
                        </Card.Footer> -->
                    </Card.Root>
                </div>
                {/each}
            </div>

        </div>

    </div>
</div>
