# Button Component

Try it out in the[`playground`](https://t.ly/-ii6V).

![image](https://github.com/shahzodsharifov/codex-btn/assets/99203910/7f7a93de-8f92-4f5c-9faf-7a323df93a28)

## Icons

I used icons of CodeX team, just write the name of icon without svg  

![image](https://github.com/shahzodsharifov/codex-btn/assets/99203910/a7282a02-7560-4379-8acd-9624b501ab1c)

For example, if you want to use plus.svg as a leading icon and menu.svg as trailing one, then you can:
```svelte
 <Button 
        text="Button"
        type="solid" 
        size="medium" 
        style="primary"
        iconType="leadingTrailing" 
        state="default" 
        leadingIcon="plus" 
        trailingIcon ="menu" />
```
## Dependencies


```
cd codex-btn
npm install
npm run dev
```


