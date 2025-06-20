<template>
    <svg xmlns="http://www.w3.org/2000/svg" width="2850" height="3449" viewBox="0 0 2850 3449" ref="metroMap">
        <path 
            v-for="(line, lineIndex) in lines" 
            :key="lineIndex"
            :id="line.id"
            :fill-rule="line.fillrule"
            :clip-path="line.clippath"
            :d="line.d"
            :fill="line.fill"
        />
        <g v-for="(station, index) in stations" :id="station.id" :key="index">
            <text
                :transform="station.transform"
                :fill="station.color1"
                :font-family="'moscowsans-medium'"
                :font-size="station.fontsize"
            > 
                {{ station.name }}
            </text>
            <rect
                :id="station.rect.id"
                :x="station.rect.x"
                :y="station.rect.y"
                :fill="station.rect.color2"
                fill-opacity="0"
                :width="station.rect.width"
                :height="station.rect.height"
            />
            <circle 
                :id="station.circle.id"
                :cx="station.circle.cx"
                :cy="station.circle.cy"
                :r="station.circle.r"
                :fill="station.circle.fill"
                :stroke="station.circle.stroke"
                :stroke-width="station.circle.strokewidth"
            />
        </g> 
    </svg>
</template>

<script>
export default {
props: {
    lines: {
        type: Array,
        required: true
    },
    stations: {
        type: Array,
        required: true
    },
},
methods: {
renderMetroMap() {

}
}
}
</script>

