<script setup>
import { portText } from '../constants';
</script>

<template>
    <section id="port">
        <div class="port_inner">
            <div class="port_title">
                portfolio <em>포폴 작업물</em>
            </div>
            <div class="port_wrap">
                <article class="port_item" v-for="(port,key) in portText" :key="key">
                    <span class="num">{{ port.num }}.</span>
                    <a :href="port.code" target="_blank" class="img">
                        <img :src="port.img" :alt="port.name" />
                    </a>
                    <h3 class="title">{{ port.title }}</h3>
                    <p class="desc">
                        {{ port.desc }}
                    </p>
                    <a :href="port.view" target="_blank" class="site">사이트보기</a>
                </article>
            </div>
        </div>
    </section>
</template>

<script>
import gsap from "gsap";
import ScrollTrigger from "gsap/ScrollTrigger";
gsap.registerPlugin(ScrollTrigger);

export default {
   mounted:function(){
    this.scrollAnimation();
   },
   methods:{
    scrollAnimation() {
        const horSection = gsap.utils.toArray(".port_item");

        gsap.to(horSection,{
            xPercent:-120*(horSection.length-1),
            ease:"none",
            scrollTrigger:{
                trigger:"#port",
                start:"top 56px",
                end:"+=3000",
                pin:true,
                scrub:1,
                markers:false,
                invalidateOnRefresh:true,
                anticipatePin:1,

            },
        });
      },
   },
};
</script>

<style lang="scss" scoped>
#port {
    width: 100%;
    margin-top: 30vh;
    overflow: hidden;
}

.port_inner {
    padding: 16px;

    .port_title {
        width: 100%;
        height: 5vw;
        font-size: 4vw;
        font-weight: 900;
        font-family: var(--mainKor-font);
        text-transform: uppercase;
        color: var(--black100);
        border-bottom: 0.4vw solid var(--black100);
        margin-bottom: 16px;
        text-indent: -0.26vw;

        @media (max-width:800px) {
            width: 100%;
            margin-bottom: 16px;
            font-size: 30px;
            height: auto;
            top: 68px;
            z-index: 1000;
            background-color: var(--mainBg-font);
        }

        em {
            font-size: 1.5rem;
            font-weight: 400;
            line-height: 2;
        }
    }

    .port_wrap {
        display: flex;
        flex-wrap: wrap;
        width: 7000px;

        .port_item {
            width: 500px;
            height: 75vh;
            background-color: var(--sugBg100);
            padding: 2.5rem;
            margin-right: 20px;

            @media (max-width:800px) {
                width: 400px;
                padding: 40px 30px;
                height: auto;
            }

            &:nth-child(1) {
                background-color: var(--subBg100);
            }
            &:nth-child(2) {
                background-color: var(--subBg200);
            }
            &:nth-child(3) {
                background-color: var(--subBg300);
            }
            &:nth-child(4) {
                background-color: var(--subBg400);
            }
            &:nth-child(5) {
                background-color: var(--subBg500);
            }
            &:nth-child(6) {
                background-color: var(--subBg100);
            }
            &:nth-child(7) {
                background-color: var(--subBg200);
            }
            &:nth-child(8){
                background-color: var(--subBg300);
            }
            &:nth-child(9) {
                background-color: var(--subBg400);
            }
            &:nth-child(10) {
                background-color: var(--subBg300);
            }
            &:nth-child(11) {
                background-color: var(--subBg300);
            }

            .num {
                font-size: 2rem;
                font-family: var(--mainNum-font);
                
            }
            .img {
                display: block;
                margin-top: -30px;
                transition: margin-top 0.2s;
                
                img {
                    border-radius: 5px;
                    filter: saturate(0);
                    transition: all 0.3s;
                }
            }

            &:hover {
                .img {
                    margin-top: -5px;
                }
                img {
                    filter: saturate(100%);
                }
            }
            .title {
                font-size: 1.5rem;
                text-align: center;
                padding: 0.8rem 0;
                font-weight: 700;
                color: var(--black100);
                border-bottom: 2px solid var(--black100);
                margin-bottom: 1rem;
            }
            .desc {
                font-size: 1rem;
            }
            .site {
                border: 1px solid var(--black100);
                display: block;
                text-align: center;
                padding: 0.625rem 1.5rem;
                margin-top: 1.5rem;
                &:hover {
                    background-color: var(--black100);
                    color: var(--white);
                }
            }
        }
    }
}
</style>