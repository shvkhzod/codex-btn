<script lang="ts"  >
	import { onMount } from "svelte";
	import { writable } from "svelte/store";





   
    


    export let text:string
    export let type:"solid" | "outline" | "soft" | "ghost"
    export let size: "small"  | "medium" | "large"
    export let style: "primary" | "secondary" | "danger"
    export let iconType: "none" | "leading" | "trailing" | "leadingTrailing"| "standalone";
    export let state:"default" | "hover" | "disabled"
    export let leadingIcon: "none" | string 
    export let trailingIcon: "none" | string


    const usedColorState = writable("")
    const softColor = writable("")
    const hoverColor = writable("")
    const textColor = writable("")

    const usedSize = writable()
    const invertPer = writable()
    const sepiaPer = writable()
    const saturatePer = writable()
    const hueRotatePer = writable()
    const brightnessPer = writable()
    const contrastPer = writable()

    onMount(()=> {


        if(style == "primary") {
            usedColorState.set("#369FFF")
            softColor.set("#369FFF1F")
            hoverColor.set("#369FFF38")
            textColor.set("#369FFF")

            invertPer.set(52)
            sepiaPer.set(15)
            saturatePer.set(3845)
            hueRotatePer.set(184)
            brightnessPer.set(102)
            contrastPer.set(101)

        }

        if(style == "secondary") {
            usedColorState.set("#30343B")
            softColor.set("#30343B1F")
            hoverColor.set("#30343B")
            textColor.set("#FFFFFFB2")

            invertPer.set(82)
            sepiaPer.set(1)
            saturatePer.set(595)
            hueRotatePer.set(33)
            brightnessPer.set(90)
            contrastPer.set(88)

            
        }

        if(style == "danger") {
            usedColorState.set("#D32A2A")
            softColor.set("#D32A2A1F")
            hoverColor.set("#D32A2A33")
            textColor.set("#D32A2A")

            invertPer.set(17)
            sepiaPer.set(56)
            saturatePer.set(5769)
            hueRotatePer.set(357)
            brightnessPer.set(96)
            contrastPer.set(84)
        }

        if(size == "small") {
            usedSize.set(4)
        }

        if(size == "medium") {
            usedSize.set(8)
        }

        if(size == "large") {
            usedSize.set(12)
        }

     

    })







    
    
</script>


<button 
class={`${type} ${size} ${style} ${iconType} ${state}`} 
style={`
--usedColor: ${$usedColorState};
--softBg: ${$softColor};
--baseSize: ${$usedSize}px;
--usedFilter: invert(${$invertPer}%) sepia(${$sepiaPer}%) saturate(${$saturatePer}%) hue-rotate(${$hueRotatePer}deg) brightness(${$brightnessPer}%) contrast(${$contrastPer}%);
--hoverColor: ${$hoverColor};
--textColor : ${$textColor};
`}

>
<img 
class={iconType == "none" || iconType == "trailing" ? "hide" : "show" } 
src={iconType == "leading" || iconType=="leadingTrailing" || iconType=="standalone" ? `/${leadingIcon}.svg`: ""} 
alt="firstIcon" />
<p class={iconType=="standalone" ? "hideText" : "showText"}>{text}</p>
<img class={iconType == "none" || iconType == "leading"|| iconType == "standalone" ? "hide" : "show" } 
src={iconType == "trailing" || iconType == "leadingTrailing" ? `/${trailingIcon}.svg` : ""} alt="second icon"/>
</button>

<style>

    button {
        --primaryColor:#369FFF;
        --secondaryColor: #30343B;
        --dangerColor: #D32A2A;
        
        --textHightContrast: #FFFFFF;
        --textSoftContrast: #FFFFFFB2;
        --textLowContrast: #94979A;

        
         
        
        font-size: 14px;
        border-radius: 8px;
        color: white;
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: space;


    }

            
        

    .solid {
     
        /* clip-path: polygon(100% 50%, 100% 56.6%, 100% 59.3%, 100% 61.4%, 99.9% 63.2%, 99.9% 64.8%, 99.9% 66.2%, 99.8% 67.5%, 99.8% 68.7%, 99.7% 69.8%, 99.6% 70.8%, 99.5% 71.8%, 99.5% 72.8%, 99.4% 73.7%, 99.3% 74.6%, 99.1% 75.4%, 99% 76.3%, 98.9% 77%, 98.8% 77.8%, 98.6% 78.5%, 98.5% 79.2%, 98.3% 79.9%, 98.1% 80.6%, 98% 81.3%, 97.8% 81.9%, 97.6% 82.5%, 97.4% 83.1%, 97.2% 83.7%, 97% 84.3%, 96.8% 84.8%, 96.5% 85.4%, 96.3% 85.9%, 96% 86.4%, 95.8% 86.9%, 95.5% 87.4%, 95.3% 87.9%, 95% 88.3%, 94.7% 88.8%, 94.4% 89.2%, 94.1% 89.7%, 93.8% 90.1%, 93.4% 90.5%, 93.1% 90.9%, 92.8% 91.3%, 92.4% 91.7%, 92% 92%, 91.7% 92.4%, 91.3% 92.8%, 90.9% 93.1%, 90.5% 93.4%, 90.1% 93.8%, 89.7% 94.1%, 89.2% 94.4%, 88.8% 94.7%, 88.3% 95%, 87.9% 95.3%, 87.4% 95.5%, 86.9% 95.8%, 86.4% 96%, 85.9% 96.3%, 85.4% 96.5%, 84.8% 96.8%, 84.3% 97%, 83.7% 97.2%, 83.1% 97.4%, 82.5% 97.6%, 81.9% 97.8%, 81.3% 98%, 80.6% 98.1%, 79.9% 98.3%, 79.2% 98.5%, 78.5% 98.6%, 77.8% 98.8%, 77% 98.9%, 76.3% 99%, 75.4% 99.1%, 74.6% 99.3%, 73.7% 99.4%, 72.8% 99.5%, 71.8% 99.5%, 70.8% 99.6%, 69.8% 99.7%, 68.7% 99.8%, 67.5% 99.8%, 66.2% 99.9%, 64.8% 99.9%, 63.2% 99.9%, 61.4% 100%, 59.3% 100%, 56.6% 100%, 50% 100%, 43.4% 100%, 40.7% 100%, 38.6% 100%, 36.8% 99.9%, 35.2% 99.9%, 33.8% 99.9%, 32.5% 99.8%, 31.3% 99.8%, 30.2% 99.7%, 29.2% 99.6%, 28.2% 99.5%, 27.2% 99.5%, 26.3% 99.4%, 25.4% 99.3%, 24.6% 99.1%, 23.7% 99%, 23% 98.9%, 22.2% 98.8%, 21.5% 98.6%, 20.8% 98.5%, 20.1% 98.3%, 19.4% 98.1%, 18.7% 98%, 18.1% 97.8%, 17.5% 97.6%, 16.9% 97.4%, 16.3% 97.2%, 15.7% 97%, 15.2% 96.8%, 14.6% 96.5%, 14.1% 96.3%, 13.6% 96%, 13.1% 95.8%, 12.6% 95.5%, 12.1% 95.3%, 11.7% 95%, 11.2% 94.7%, 10.8% 94.4%, 10.3% 94.1%, 9.9% 93.8%, 9.5% 93.4%, 9.1% 93.1%, 8.7% 92.8%, 8.3% 92.4%, 8% 92%, 7.6% 91.7%, 7.2% 91.3%, 6.9% 90.9%, 6.6% 90.5%, 6.2% 90.1%, 5.9% 89.7%, 5.6% 89.2%, 5.3% 88.8%, 5% 88.3%, 4.7% 87.9%, 4.5% 87.4%, 4.2% 86.9%, 4% 86.4%, 3.7% 85.9%, 3.5% 85.4%, 3.2% 84.8%, 3% 84.3%, 2.8% 83.7%, 2.6% 83.1%, 2.4% 82.5%, 2.2% 81.9%, 2% 81.3%, 1.9% 80.6%, 1.7% 79.9%, 1.5% 79.2%, 1.4% 78.5%, 1.2% 77.8%, 1.1% 77%, 1% 76.3%, 0.9% 75.4%, 0.7% 74.6%, 0.6% 73.7%, 0.5% 72.8%, 0.5% 71.8%, 0.4% 70.8%, 0.3% 69.8%, 0.2% 68.7%, 0.2% 67.5%, 0.1% 66.2%, 0.1% 64.8%, 0.1% 63.2%, 0% 61.4%, 0% 59.3%, 0% 56.6%, 0% 50%, 0% 43.4%, 0% 40.7%, 0% 38.6%, 0.1% 36.8%, 0.1% 35.2%, 0.1% 33.8%, 0.2% 32.5%, 0.2% 31.3%, 0.3% 30.2%, 0.4% 29.2%, 0.5% 28.2%, 0.5% 27.2%, 0.6% 26.3%, 0.7% 25.4%, 0.9% 24.6%, 1% 23.7%, 1.1% 23%, 1.2% 22.2%, 1.4% 21.5%, 1.5% 20.8%, 1.7% 20.1%, 1.9% 19.4%, 2% 18.7%, 2.2% 18.1%, 2.4% 17.5%, 2.6% 16.9%, 2.8% 16.3%, 3% 15.7%, 3.2% 15.2%, 3.5% 14.6%, 3.7% 14.1%, 4% 13.6%, 4.2% 13.1%, 4.5% 12.6%, 4.7% 12.1%, 5% 11.7%, 5.3% 11.2%, 5.6% 10.8%, 5.9% 10.3%, 6.2% 9.9%, 6.6% 9.5%, 6.9% 9.1%, 7.2% 8.7%, 7.6% 8.3%, 8% 8%, 8.3% 7.6%, 8.7% 7.2%, 9.1% 6.9%, 9.5% 6.6%, 9.9% 6.2%, 10.3% 5.9%, 10.8% 5.6%, 11.2% 5.3%, 11.7% 5%, 12.1% 4.7%, 12.6% 4.5%, 13.1% 4.2%, 13.6% 4%, 14.1% 3.7%, 14.6% 3.5%, 15.2% 3.2%, 15.7% 3%, 16.3% 2.8%, 16.9% 2.6%, 17.5% 2.4%, 18.1% 2.2%, 18.7% 2%, 19.4% 1.9%, 20.1% 1.7%, 20.8% 1.5%, 21.5% 1.4%, 22.2% 1.2%, 23% 1.1%, 23.7% 1%, 24.6% 0.9%, 25.4% 0.7%, 26.3% 0.6%, 27.2% 0.5%, 28.2% 0.5%, 29.2% 0.4%, 30.2% 0.3%, 31.3% 0.2%, 32.5% 0.2%, 33.8% 0.1%, 35.2% 0.1%, 36.8% 0.1%, 38.6% 0%, 40.7% 0%, 43.4% 0%, 50% 0%, 56.6% 0%, 59.3% 0%, 61.4% 0%, 63.2% 0.1%, 64.8% 0.1%, 66.2% 0.1%, 67.5% 0.2%, 68.7% 0.2%, 69.8% 0.3%, 70.8% 0.4%, 71.8% 0.5%, 72.8% 0.5%, 73.7% 0.6%, 74.6% 0.7%, 75.4% 0.9%, 76.3% 1%, 77% 1.1%, 77.8% 1.2%, 78.5% 1.4%, 79.2% 1.5%, 79.9% 1.7%, 80.6% 1.9%, 81.3% 2%, 81.9% 2.2%, 82.5% 2.4%, 83.1% 2.6%, 83.7% 2.8%, 84.3% 3%, 84.8% 3.2%, 85.4% 3.5%, 85.9% 3.7%, 86.4% 4%, 86.9% 4.2%, 87.4% 4.5%, 87.9% 4.7%, 88.3% 5%, 88.8% 5.3%, 89.2% 5.6%, 89.7% 5.9%, 90.1% 6.2%, 90.5% 6.6%, 90.9% 6.9%, 91.3% 7.2%, 91.7% 7.6%, 92% 8%, 92.4% 8.3%, 92.8% 8.7%, 93.1% 9.1%, 93.4% 9.5%, 93.8% 9.9%, 94.1% 10.3%, 94.4% 10.8%, 94.7% 11.2%, 95% 11.7%, 95.3% 12.1%, 95.5% 12.6%, 95.8% 13.1%, 96% 13.6%, 96.3% 14.1%, 96.5% 14.6%, 96.8% 15.2%, 97% 15.7%, 97.2% 16.3%, 97.4% 16.9%, 97.6% 17.5%, 97.8% 18.1%, 98% 18.7%, 98.1% 19.4%, 98.3% 20.1%, 98.5% 20.8%, 98.6% 21.5%, 98.8% 22.2%, 98.9% 23%, 99% 23.7%, 99.1% 24.6%, 99.3% 25.4%, 99.4% 26.3%, 99.5% 27.2%, 99.5% 28.2%, 99.6% 29.2%, 99.7% 30.2%, 99.8% 31.3%, 99.8% 32.5%, 99.9% 33.8%, 99.9% 35.2%, 99.9% 36.8%, 100% 38.6%, 100% 40.7%, 100% 43.4%); */
        border: none;
        background-color: var(--usedColor);
        color: var(--textHightContrast);

       
       
    }

    .outline {
        background-color: transparent;
        border: 1px solid var(--hoverColor);
        color: var(--textColor)
       
    }



   .soft {
        background-color: var(--softBg);
        border: none;
        color:  var(--textColor);
 
   } 
   .ghost {
        background-color: transparent;
        border: none;
        color: var(--textColor);

        
       
   }



   
   .outline  img.show {
       filter: var(--usedFilter)
    }

    .soft img.show {
        filter: var(--usedFilter)
    }
   
   .ghost  img.show {
       filter: var(--usedFilter)
    }



    .solid.hover {
        border: none;
        background-color: #0274DC;
        color: var(--textHightContrast);
    }

    .solid.secondary.hover {
        background-color: #1A1B1C;
    }

    .solid.danger.hover {
        background-color: #8A1D1D;
    }

    .outline.hover {
        background-color: #369FFF38;
        border: 1px solid var(--hoverColor);
        color: var(--textColor)
    }

    .outline.secondary.hover {
        background-color: #30343BB2;
     
    }

    .outline.danger.hover {
        background-color: #D32A2A33;
       
    }

    .soft.hover {
        background-color: #369FFF1F;
        border: none;
        color:  var(--textColor);
 
   } 

   .soft.secondary.hover {
    background-color: #369FFF38;
   }

   .soft.danger.hover {
    background-color: #D32A2A33;
   }

   .ghost.hover {
    background-color: #369FFF1F;

   }

   .ghost.secondary.hover {
    background-color: #30343B80;

   }

   .ghost.danger.hover {
    background-color: #D32A2A1F;
   }

   

   .solid.disabled {
    background-color: #30343B;
    color: #94979A;
   }

   .soft.disabled {
    background-color: #30343B80;
   }

   .outline.disabled {
    border: 1px solid #38393B;

   }

   .ghost.disabled {
    border: none;
    color: #94979A;
   }

   .solid.disabled img.show {
    filter: invert(63%) sepia(3%) saturate(313%) hue-rotate(169deg) brightness(94%) contrast(91%);
   }

   
   .outline.disabled img.show {
    filter: invert(63%) sepia(3%) saturate(313%) hue-rotate(169deg) brightness(94%) contrast(91%);
   }

   
   .soft.disabled img.show {
    filter: invert(63%) sepia(3%) saturate(313%) hue-rotate(169deg) brightness(94%) contrast(91%);
   }


   .ghost.disabled img.show {
    filter: invert(63%) sepia(3%) saturate(313%) hue-rotate(169deg) brightness(94%) contrast(91%);
   }





    


 

 




   .none {
        padding-top: var(--baseSize);
        padding-bottom: var(--baseSize);
        padding-right:  calc(var(--baseSize) + (var(--baseSize) + 4px));
        padding-left:  calc(var(--baseSize) + (var(--baseSize) + 4px));
    }


    .leading {
      
        padding-top: var(--baseSize);
        padding-bottom: var(--baseSize);
        padding-left: var(--baseSize);
        padding-right: calc(var(--baseSize) + (var(--baseSize) + 4px));
    }

    .trailing {
        padding-top: var(--baseSize);
        padding-bottom: var(--baseSize);
        padding-right: var(--baseSize);
        padding-left:  calc(var(--baseSize) + (var(--baseSize) + 4px));
    }

    .leadingTrailing {
        padding: var(--baseSize);
    }

    .standalone {
        padding: var(--baseSize);
    }

 





    

    img.hide {
        display: none;
    }
 img.show {
    filter: invert(100%) sepia(0%) saturate(2%) hue-rotate(89deg) brightness(104%) contrast(101%);
    }

    .hideText {
        display: none;
    }


    

   
</style>