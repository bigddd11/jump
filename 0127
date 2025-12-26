(function() {
    /******************************
     * 截止日期配置区域（请在此修改）
     ******************************/
    const DEADLINE_CONFIG = {
        year: 2025,   // 年份（实际年份）
        month: 12,    // 月份（1-12，代表实际月份）
        day: 27,      // 日期（1-31）
        hours: 23,    // 小时（0-23）
        minutes: 59,  // 分钟（0-59）
        seconds: 59   // 秒（0-59）
    };

    /******************************
     * 主逻辑区域（一般无需修改）
     ******************************/
    let currentDate = new Date();
    // 使用配置生成截止日期（月份需-1以符合JavaScript规范）
    let deadline = new Date(
        DEADLINE_CONFIG.year,
        DEADLINE_CONFIG.month - 1,  // JavaScript月份从0开始
        DEADLINE_CONFIG.day,
        DEADLINE_CONFIG.hours,
        DEADLINE_CONFIG.minutes,
        DEADLINE_CONFIG.seconds
    );
    
    if (currentDate > deadline) {
        $done({});
        return;
    }

    let body = $response.body;
    
    try {
        let jsonData = JSON.parse(body);
        
        if (jsonData && jsonData.data && Array.isArray(jsonData.data)) {
            for (let item of jsonData.data) {
                if (item.itemKey === 'coalMineSignUpNoticeConfigV2') {
                    item.itemValue = "1";
                    break;
                }
            }
            
            $done({body: JSON.stringify(jsonData)});
        } else {
            $done({});
        }
    } catch (error) {
        $done({});
    }
})();
