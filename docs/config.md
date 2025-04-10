| 配置项                    | 默认值                                     | 描述                                                                                        |
|------------------------|-----------------------------------------|-------------------------------------------------------------------------------------------|
| open_service           | True                                    | 开启页面服务，用于控制是否启动结果页面服务；如果使用青龙等平台部署，有专门设定的定时任务，需要更新完成后停止运行，可以关闭该功能                          |
| open_update            | True                                    | 开启更新，用于控制是否更新接口，若关闭则所有工作模式（获取接口和测速）均停止                                                    |
| open_use_old_result    | True                                    | 开启使用历史更新结果（包含模板与结果文件的接口），合并至本次更新中                                                         |
| open_use_cache         | True                                    | 开启使用本地缓存数据，适用于查询请求失败场景                                                                    |
| open_request           | False                                   | 开启查询请求，数据来源于网络                                                                            |
| open_driver            | True                                    | 开启浏览器运行，若更新无数据可开启此模式，较消耗性能                                                                |
| open_proxy             | False                                   | 开启代理，自动获取免费可用代理，若更新无数据可开启此模式                                                              |
| source_file            | config/demo.txt                         | 模板文件路径                                                                                    |
| final_file             | output/result.txt                       | 生成结果文件路径                                                                                  |
| open_online_search     | False                                   | 开启关键字搜索源功能                                                                                |
| online_search_page_num | 1                                       | 关键字搜索频道获取分页数量                                                                             |
| urls_limit             | 10                                      | 单个频道接口数量                                                                                  |
| open_keep_all          | False                                   | 保留所有检索结果，会保留非模板频道名称的结果，推荐手动维护时开启                                                          |
| open_sort              | True                                    | 开启排序功能（响应速度、日期、分辨率）                                                                       |
| sort_timeout           | 5                                       | 单个接口测速超时时长，单位秒(s)；数值越大测速所属时间越长，能提高获取接口数量，但质量会有所下降；数值越小测速所需时间越短，能获取低延时的接口，质量较好；调整此值能优化更新时间 |
| open_ffmpeg            | True                                    | 开启使用 FFmpeg 进行测速，获取更准确的速度与分辨率信息，需要提前手动安装                                                  |
| open_m3u_result        | True                                    | 开启转换生成 m3u 文件类型结果链接，支持显示频道图标                                                              |
| open_filter_speed      | True                                    | 开启速率过滤，低于最小速率（min_speed）的接口将会被过滤                                                          |
| min_speed              | 0.5                                     | 接口最小速率（单位M/s），需要开启 open_filter_speed 才能生效                                                 |
| open_filter_resolution | True                                    | 开启分辨率过滤，低于最小分辨率（min_resolution）的接口将会被过滤                                                   |
| min_resolution         | 1920x1080                               | 接口最小分辨率，需要开启 open_filter_resolution 才能生效                                                  |
| speed_weight           | 0.5                                     | 速率权重值（所有权重值总和应为 1）                                                                        |
| delay_weight           | 0.25                                    | 响应时间权重值（所有权重值总和应为 1）                                                                      |
| resolution_weight      | 0.25                                    | 分辨率权重值 （所有权重值总和应为 1）                                                                      |
| recent_days            | 30                                      | 获取最近时间范围内更新的接口（单位天），适当减小可避免出现匹配问题                                                         |
| ipv_type               | 全部                                      | 生成结果中接口的协议类型，可选值：ipv4、ipv6、全部、all                                                         |
| ipv_type_prefer        | 自动                                      | 接口协议类型偏好，优先将该类型的接口排在结果前面，可选值：IPv4、IPv6、自动、auto                                            |
| ipv4_num               | 5                                       | 结果中偏好的 IPv4 接口数量                                                                          |
| ipv6_num               | 5                                       | 结果中偏好的 IPv6 接口数量                                                                          |
| url_keywords_blacklist |                                         | 接口关键字黑名单，用于过滤含特定字符的接口                                                                     |
| open_subscribe         | False                                   | 开启订阅源功能                                                                                   |
| subscribe_urls         |                                         | 订阅源，请输入订阅链接（支持 txt 与 m3u 链接），多个链接以逗号分隔                                                    |
| open_multicast         | True                                    | 开启组播源功能，关闭后所有组播源工作模式都将关闭                                                                  |
| open_multicast_foodie  | True                                    | 开启 Foodie 组播源工作模式                                                                         |
| open_multicast_fofa    | True                                    | 开启 FOFA 组播源工作模式                                                                           |
| multicast_region_list  | 全部                                      | 组播源地区列表，[更多地区](../updates/multicast/multicast_map.json)，"全部"表示所有地区                        |
| multicast_page_num     | 1                                       | 组播地区获取分页数量                                                                                |
| open_hotel             | True                                    | 开启酒店源功能，关闭后所有酒店源工作模式都将关闭                                                                  |
| open_hotel_foodie      | True                                    | 开启 Foodie 酒店源工作模式                                                                         |
| open_hotel_fofa        | True                                    | 开启 FOFA、ZoomEye 酒店源工作模式                                                                   |
| hotel_region_list      | 全部                                      | 酒店源地区列表，[更多地区](../updates/fofa/fofa_map.py)，"全部"表示所有地区                                    |
| hotel_page_num         | 1                                       | 酒店地区获取分页数量                                                                                |
| request_timeout        | 10                                      | 查询请求超时时长，单位秒(s)，用于控制查询接口文本链接的超时时长以及重试时长，调整此值能优化更新时间                                       |
| origin_type_prefer     | hotel,multicast,subscribe,online_search | 结果偏好的接口来源，结果优先按该顺序进行排序，hotel：酒店源，multicast：组播源，subscribe：订阅源，online_search：关键字搜索          |
| hotel_num              | 4                                       | 结果中偏好的酒店源接口数量                                                                             |
| multicast_num          | 3                                       | 结果中偏好的组播源接口数量                                                                             |
| subscribe_num          | 3                                       | 结果中偏好的订阅源接口数量                                                                             |
| online_search_num      | 0                                       | 结果中偏好的关键字搜索接口数量                                                                           |
| open_url_info          | True                                    | 开启显示接口说明信息，用于控制是否显示分辨率、接口协议类型等信息，为$符号后的内容，播放软件使用该信息对接口进行描述                                |
| open_empty_category    | False                                   | 开启无结果频道分类，自动归类至底部                                                                         |
| open_update_time       | True                                    | 开启显示更新时间                                                                                  |