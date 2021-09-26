![Reda Ennakouri](https://raw.githubusercontent.com/redaEnnakouri/vue-twitch-video-controls/main/images/royalCode.jpeg)

# Package vue-twitch-video-controls
the objective of this package is to embed video twitch  with use all controls in Vue js

![Reda Ennakouri](https://camo.githubusercontent.com/03f7e55f3cae2f2677b0f8b7e899d7aa3a6514075fe2581514fa0fe79f97e471/68747470733a2f2f6d6963726f77656265722e636f6d2f63646e2f323031395f76657273696f6e2f537461722d4d6963726f77656265722e676966)

# Npm
Link of the package at NPM : https://www.npmjs.com/package/vue-twitch-video-controlls

# Install package
install package with commande `npm i vue-twitch-video-controlls`

# Import Component 

```
<template>
    <vue-twitch-video-controlles />
</template>
   
   <script>
import VueTwitchVideoControlles from "@/vue-twitch-video-controlles.vue";

export defiault {
  components: {
    VueTwitchVideoControlles,
  }
};
</script>
```

# Video Control
For control video you need to send props to component like :

* video :String (you need to import id video at twitch)
* width :String
* height :String
* mute :Boolean
* autoplay :Boolean
* controls :Boolean (show controls video)
* allowfullscreen :Boolean

For Exemple :
``` 
<template>
     <vue-twitch-video-controlles
      :video="1148356867"
      :controls="true"
      :mute="false"
    />
</template>
   
   <script>
import VueTwitchVideoControlles from "@/vue-twitch-video-controlles.vue";

export defiault {
  components: {
    VueTwitchVideoControlles,
  }
};
</script>
```

# Buttons Controls
for hide buttons Controls you can send props `:allowButtons =false`

```
<template>
     <vue-twitch-video-controlles
      :video="1148356867"
      :allowButtons =false
    />
</template>
   
   <script>
import VueTwitchVideoControlles from "@/vue-twitch-video-controlles.vue";

export defiault {
  components: {
    VueTwitchVideoControlles,
  }
};
</script>
```






