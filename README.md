# 16P Checkout page

Small test assignment. Publicly available on [https://16personalities-checkout.netlify.app/](netlify).

## Done

- implement via `vue create`
- decomposition into small components
- show different - but simple - types of how to work with assets
- full compliance with the design

ps. in forms autocomplete switched on by default, the main thing there is that names attributes has correct values. 

## Critical notes

Basically, as a react-developer, I prefer it's characteristic best practices:

1. As for naming for components and css classnames - I prefer CamelCase instead of `<dash-divider>`;
2. I use css-modules, from my opinion it's much useful, but we can switch to scoped styles as well; 
3. We can use BEM for css class-naming;
4. I didn't use `less`, it was not necessary;

<b>General conclusion</b>

All these things can and must be improved according to specific rules and code-style that is accepted in the team by default (including such good tools as linters and prettier).

## Not done

 - Tooltip background shape (can't be extracted from Zeplin)
 - passing html (link) via text string inside Info section
 - checkboxes do nothing (don't change state of other components)
 - didn't implement tooltip for question mark icon, cos' usually better to use some specific library or package.

## Todo

- add validation for form elements
- optimize components (styles, props composition etc)
- create storybook
- add prettier
- add typescript + tslint