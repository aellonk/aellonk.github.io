---
layout: post
title:      "Multilingual Magic"
date:       2020-04-10 19:58:28 -0400
permalink:  multilingual_magic
---


I'm currently building a site using Wordpress and Bootstrap that will have the option for users to see featured content in English, Spanish, and Russian. I needed to make this happen dynamically, and so it would be displayed seamlessly to the user. I also needed it to be easy for the client to update on the backend in Wordpress. 

I am already using Bootstrap in the project, so it is easy to implement Bootstrap tabs using the class `.nav-tabs ` on top of the base `.nav` component. I could have used tabs or pills because they just have different styling. Since I am going to change the styling anyway, I went with tabs for fun. 

```
<ul class="nav nav-tabs" id="alertTab" role="tablist">
     <li class="nav-item">
         <a class="nav-link active" id="english-tab" data-toggle="tab" href="#english" role="tab" aria-controls="english" aria-selected="true">EN</a>
     </li>
     <li class="divider text-red">|</li>
     <li class="nav-item">
         <a class="nav-link" id="russian-tab" data-toggle="tab" href="#russian" role="tab" aria-controls="russian" aria-selected="false">RU</a>
     </li>
     <li class="divider text-red">|</li>
     <li class="nav-item">
         <a class="nav-link" id="spanish-tab" data-toggle="tab" href="#spanish" role="tab" aria-controls="spanish" aria-selected="false">SP</a>
     </li>
</ul>
```

An important [note on accessibility from Bootstrap](https://getbootstrap.com/docs/4.4/components/navs/#javascript-behavior):
> Dynamic tabbed interfaces, as described in the WAI ARIA Authoring Practices, require role="tablist", role="tab", role="tabpanel", and additional aria- attributes in order to convey their structure, functionality and current state to users of assistive technologies (such as screen readers).

There is a tab for English, Spanish, and Russian, and I'm using simple vertical line dividers to separate the three tabs. To make the tabs toggleable, we need to add the attribute `data-toggle="tab"` to each tab link.  Now we need to add in the JavaScript behavior to make the tabs dynamic.  

Make a new div with a class of `.tab-content` and add three divs inside, each with a `.tab-pane` class and a unique ID for every tab that will correspond to the href element in each of the tabs above.

```
<div class="tab-content" id="alertTabContent">
        <div class="tab-pane fade show active" id="english" role="tabpanel" aria-labelledby="english-tab">
            <a href="<?php echo esc_url( get_permalink($id) ); ?>">
                <h5 class="text-dark-red alert-content"><?php  the_content(); ?></h5>
            </a>
        </div>
        <div class="tab-pane fade" id="russian" role="tabpanel" aria-labelledby="russian-tab">
            <a href="<?php echo esc_url( get_permalink($id) ); ?>">
                <h5 class="text-dark-red alert-content"><?php the_field('russian'); ?></h5>
            </a>
        </div>
        <div class="tab-pane fade" id="spanish" role="tabpanel" aria-labelledby="spanish-tab">
            <a href="<?php echo esc_url( get_permalink($id) ); ?>">
                <h5 class="text-dark-red alert-content"><?php the_field('spanish'); ?></h5>
            </a>
        </div>
</div>```


Next time we will connect it to the Wordpress backend in order to pull in content dynamically. Stay tuned!





Resources:
[Bootstrap Tabs](https://getbootstrap.com/docs/4.4/components/navs/#tabs)
