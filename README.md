# Package vue-twitch-video-controls
the objective of this package is to embed video twitch  with use all controlls in Vue js

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

# Result 

![Reda Ennakouri](https://drive.google.com/file/d/1BZyM_OVcKawaoTrEggkYUnynjDmZb4Cz/view?usp=sharing)








