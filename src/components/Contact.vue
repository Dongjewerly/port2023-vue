<script setup>
import { contactText } from '../constants';
</script>

<template>
    <section id="contact">
        <div class="contact_inner">
            <h2 class="contact_title">Contact</h2>
            <div class="contact_lines top" aria-hidden="true">
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
            </div>
            <div class="contact_text">
                <div class="text" v-for="(contact,key) in contactText" :key="key">
                    <div>
                        <a href="contact.link" target="_blank">{{ contact.title }}</a>
                    </div>
                </div>
            </div>
            <div class="contact_lines bottom" aria-hidden="true">
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
            </div>
        </div>
    </section>
</template>

<style lang="scss">
#contact {
    height: 100vh;
}
.contact_inner {
    width: 100%;
    height: 100%;
    padding: 16px;
    display: flex;
    align-items: flex-start;
    justify-content: flex-end;
    flex-direction: column;

    @media (max-width: 800px){ 
        justify-content: center;
    }
    .contact_title {
        font-size: 10vw;
        text-transform: uppercase;
        line-height: 1;
        font-weight: 800;
        white-space: nowrap;
        text-indent: -0.5vw;
        letter-spacing: -0.3vw;

        @media (max-width:800px){
            display: none;
        }
    }
    .contact_text {
        width: 100%;
        height: 40vh;
        background-color: var(--black);
        color: var(--white);
        display: flex;
        align-items: center;
        justify-content: center;
        flex-direction: column;
        position: relative;

        .text {
            font-size: 3vw;
            line-height: 1;
            font-weight: 900;
            text-transform: uppercase;
            text-decoration: underline;
            text-align: center;
            position: relative;
            z-index: 100;
            transition: all 0.3s;
            cursor: all-scroll;
            
            @media (max-width:800px) {
                font-size: 24px;
                padding: 0 16px;
                word-break: break-all;
            }

            
        }
    
    }
    .contact_lines {
        width: 100%;

        .line {
            display: block;
            width: 100%;
            height: 1px;
            background-color: var(--black);
            margin-bottom: 0.5vw;

            &:nth-child(1){
                height: 25px;
            }
            &:nth-child(2){
                height: 17px;
            }
            &:nth-child(3){
                height: 13px;
            }
            &:nth-child(4){
                height: 9px;
            }
            &:nth-child(5){
                height: 5px;
            }
            &:nth-child(6){
                height: 2px;
            }
            &:nth-child(7){
                height: 1px;
            }
        
        }

        &.top {
            .line {
                margin-top: 0.5vw;
                margin-bottom: 0;
                display: none;

                @media (max-width:800px) {
                    display: block;
                    
                }

                &:nth-child(7){
                    height: 25px;
                }
                &:nth-child(6){
                    height: 17px;
                }
                &:nth-child(5){
                    height: 13px;
                }
                &:nth-child(4){
                    height: 9px;
                }
                &:nth-child(3){
                    height: 5px;
                }
                &:nth-child(2){
                    height: 2px;
                }
                &:nth-child(1){
                    height: 1px;
                }

            }
        }
    }
    
    
}
</style>