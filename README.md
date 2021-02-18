# flomo-raycast
raycast脚本发送到flomo（mac类alfred启动器）

下述脚本 flomo.sh
放到 RaycastScripts/script-commands/_enabled-commands里，raycast就可以加载了。

使用方法：

唤起raycast

输入：flomo 空格 想输入的文本

enter

————————————
脚本内容：

    #!/bin/bash
    
    # Dependency: xxx
    # Install via npm: `npm install --global xxx`
    
    # @raycast.title flomo
    # @raycast.author xinqiji
    # @raycast.authorURL https://alotus.com.cn
    # @raycast.description Add text to flomo
    
    # @raycast.icon 📙
    # @raycast.mode compact
    # fullOutput：命令在单独的视图中打印整个输出。
    # compact：命令在 Raycast 窗口下方运行并打印结果。
    # silent: 命令关闭 Raycast 窗口并在后台运行。
    # inline：将脚本设置为以刷新仪表板的方式显示，支持配置参数 refreshTime。
    
    # @raycast.packageName Apps
    # @raycast.schemaVersion 1
    
    # @raycast.argument1 { "type": "text", "placeholder": "input text for flomo ..." }
    
    
    curl -X POST 你的api地址 \
         -H 'Content-Type: application/json' \
         -d "{\"content\": \"$1\"}" \
         &>flomo_sh_result.txt
    
    echo "发送到flomo成功！"
