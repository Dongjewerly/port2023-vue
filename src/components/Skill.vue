<script setup>
import {skillText} from "@/constants/index";
</script>

<template>
    <section id="skill">
        <div class="skill_inner">
            <h2 class="skill_title">
                challenge <em>나의 도전</em>
            </h2>
            <div class="skill_desc">
                <div v-for="(skill,key) in skillText" :key="key">
                    <span>{{ key+1 }}.</span>
                    <h3>{{ skill.title }}</h3>
                    <p>{{ skill.desc }}</p>
                </div>
            </div>
        </div>
    </section>
</template>

<style lang="scss" scoped>
.skill_inner {
    padding: 16px;
    display: flex;
    justify-content: space-between;

    @media (max-width: 800px) {
        flex-direction: column;
    }

    .skill_title {
        position: sticky; 
        top: 70px;
        left: 0;
        width: 48%;
        height: 5.1vw;
        font-weight: 900;
        font-size: 4vw;
        line-height: 1.6;
        font-family: var(--mainKor-font);
        text-transform: uppercase;
        color: var(--black100);
        border-bottom: 0.4vw solid var(--black100);

        @media (max-width: 800px) {
            width: 100%;
            margin-bottom: 10vw;
            font-size: 30px;
            height: auto;
            top: 68px;
            background-color: var(--mainBg-color);
        }

        em {
            font-size: 1.5rem;
            font-weight: 400;
            line-height: 2;
        }
    }

    .skill_desc {
        width: 50%;

        @media (max-width: 800px) {
            width: 100%;
        }

        span {
            font-size: 5vw;
            line-height: 1.3;
            font-weight: 900;
            font-family: var(--mainNum-font);

            @media (max-width: 800px) {
                font-size: 20vw;
            }

        }


        h3 {
            font-size: 1.5rem;
            text-decoration: underline;
            text-underline-position: under;
            margin-bottom: 1vw;
        }

        p {
            margin-bottom: 30vh;
            font-size: 1.1rem;
        }
    }
}
</style>