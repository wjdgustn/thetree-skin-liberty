<template>
    <setting>
        <setting-item-select label="사이드바 설정" ckey="liberty.sidebar" :default="sidebar">
            <option value="fix">고정</option>
            <option value="hide">숨김</option>
            <option value="show">표시</option>
        </setting-item-select>
        <setting-item-checkbox label="내비게이션 바 고정" ckey="liberty.fixed_navbar" />
        <setting-item-checkbox label="페이지 이동 시 검색 창 초기화" ckey="liberty.reset_search_on_move" :default="true" />
        <setting-item-checkbox label="리비전 선택기" ckey="liberty.rev_selector" :default="true" />
        <setting-item-checkbox label="리비전 편의성 개선" ckey="liberty.rev_convenience" :default="true" />
    </setting>
</template>

<script>
import Common from '~/mixins/common';

import Setting from '~/components/setting';
import SettingItemCheckbox from '~/components/settingItemCheckbox';
import SettingItemSelect from '~/components/settingItemSelect';

import { isMobile } from '~/utils';

export default {
    mixins: [Common],
    components: {
        Setting,
        SettingItemCheckbox,
        SettingItemSelect,
    },
    computed: {
        sidebar() {
            return isMobile ? "hide" : "show";
        }
    }
}
</script>