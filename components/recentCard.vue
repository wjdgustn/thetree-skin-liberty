<template>
    <div class="live-recent-content">
        <ul class="live-recent-list" id="live-recent-list">
            <template v-if="recent.length === 0">
                <li><span class="recent-item">&nbsp;</span></li>
                <li><span class="recent-item">&nbsp;</span></li>
                <li><span class="recent-item">&nbsp;</span></li>
                <li><span class="recent-item">&nbsp;</span></li>
                <li><span class="recent-item">&nbsp;</span></li>
                <li><span class="recent-item">&nbsp;</span></li>
                <li><span class="recent-item">&nbsp;</span></li>
                <li><span class="recent-item">&nbsp;</span></li>
                <li><span class="recent-item">&nbsp;</span></li>
                <li><span class="recent-item">&nbsp;</span></li>
            </template>
            <template v-else>
                <li v-for="(r,i) in recent" :key="i">
                    <nuxt-link class="recent-item" :class="{ removed: r.status === 'delete' }" :key="r.document" :to="doc_action_link(r.document, 'w')">[<local-date :date="r.date" :format="getDateType(r.date)" />] {{ r.document }}</nuxt-link>
                </li>
            </template>
        </ul>
    </div>
</template>

<script>
import RecentCardMixin from '~/mixins/recentCard';
export default {
    mixins: [RecentCardMixin],
    methods: {
        getDateType(date) {
            const now = Math.floor((new Date()).getTime() / 1000);
            return (now - 86400) > date ? 'Y/m/d' : 'H:i:s';
        }
    }
}
</script>
