local date_string = "2024-1-2 18:02:47"

-- 将日期字符串解析为时间表
local pattern = "(%d+)-(%d+)-(%d+) (%d+):(%d+):(%d+)"
local year, month, day, hour, min, sec = date_string:match(pattern)

local time_table = {
    year = year,
    month = month,
    day = day,
    hour = hour,
    min = min,
    sec = sec
}

-- 转换为时间戳
local timestamp = os.time(time_table)