<script>
    import { onMount, onDestroy } from "svelte";
    import cloud_icon from "../../../Assets/SVG/cloud_lock.svg";
    import Lock from "../../../Assets/SVG/Lock.svg";
    import Shield from "../../../Assets/SVG/shield.svg";
    let svgAddresses = [{image: cloud_icon,title: "Data",Detail: "Protected"},{image: Lock,title: "2048",Detail: "Bit Secured"},{image: Shield,title: "SSL",Detail: "Security",}];
    let isMobile = false;
    const checkScreenWidth = () => {
        isMobile = window.innerWidth < 600;
    };
    onMount(() => {
        checkScreenWidth();
        window.addEventListener("resize", checkScreenWidth);
    });
    onDestroy(() => {
        window.removeEventListener("resize", checkScreenWidth);
    });
</script>

<div class="button_div">
    {#each svgAddresses as { image, title, Detail }}
        <div class="white_icon">
            <img class="icon_1" src={image} alt=""/>
            <div class="child_text_div">
                <p2 class="P_text_1">{title}</p2>
                <p2 class="p_text_2">{Detail}</p2>
            </div>
        </div>
    {/each}
</div>

<style>
    .child_text_div {
        display: flex;
        flex-direction: column;
    }
    .button_div {
        margin-top: 45px;
        display: flex;
        justify-content: space-between;
        justify-content: center;
        gap: 80px;
        padding-bottom: 20px;
    }
    .icon_1 {
        height: 55px;
        width: 54.3px;
        margin-left: 22.98px;
        margin-right: 16.98px;
    }
    .white_icon {
        display: flex;
        box-sizing: border-box;
        width: 235.84px;
        height: 89px;
        background: #ffffff;
        box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.15);
        border-radius: 22px;
        align-items: center;
    }

    @media (max-width: 900px) {
        .button_div {
            margin-top: 32px;
            display: flex;
            justify-content: space-between;
            justify-content: center;
            gap: 30px;
            padding-bottom: 20px;
        }
        .white_icon {
            display: flex;
            box-sizing: border-box;
            width: 25%;
            height: 79px;
            background: #ffffff;
            box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.15);
            border-radius: 10px;
            align-items: center;
        }
        .icon_1 {
            height: 45%;
            width: 30%;
            margin-left: 4.98px;
            margin-right: 2.2px;
        }
        .P_text_1 {
            font-family: Arial;
            font-size: 16px;
            font-weight: 700;
            line-height: 18px;
            letter-spacing: 0em;
            text-align: left;
        }
        .p_text_2 {
            font-family: Arial;
            font-size: 13px;
            font-weight: 400;
            line-height: 15px;
            letter-spacing: 0em;
            text-align: left;
        }
    }
    @media (max-width: 597px) {
        .button_div {
            margin-top: 32px;
            display: flex;
            justify-content: space-between;
            justify-content: center;
            gap: 10px;
            padding-bottom: 20px;
        }
        .white_icon {
            display: flex;
            box-sizing: border-box;
            width: 29%;
            height: 59px;
            background: #ffffff;
            box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.15);
            border-radius: 10px;
            align-items: center;
        }
        .icon_1 {
            height: 45%;
            width: 30%;
            margin-left: 4.98px;
            margin-right: 2.2px;
        }
        .P_text_1 {
            font-family: Arial;
            font-size: 16px;
            font-weight: 700;
            line-height: 18px;
            letter-spacing: 0em;
            text-align: left;
        }
        .p_text_2 {
            font-family: Arial;
            font-size: 13px;
            font-weight: 400;
            line-height: 15px;
            letter-spacing: 0em;
            text-align: left;
        }
    }
</style>
