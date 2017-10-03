---
title: "BAM 门户中的已知问题 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e681e910-c664-479c-86f3-a6ae0ec97775
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0aa12d0f25a004f2e713f360e00c0f0c1192d304
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-in-the-bam-portal"></a>BAM 门户中的已知的问题
本主题中包含的信息可以帮助您确定和解决使用 BAM 门户过程中可能出现的问题。  
  
## <a name="errors-are-generated-when-the-bam-portal-and-internet-explorer-7-or-internet-explorer-8-are-on-the-same-computer-and-the-security-settings-are-set-to-low"></a>BAM 门户和 Internet Explorer 7 或 Internet Explorer 8 位于同一台计算机和的安全设置设置为低时生成错误  
 **问题**  
  
 使用 Internet Explorer 7 或 Internet Explorer 7 或使用 Internet Explorer 8 时[!INCLUDE[btsWinVista](../includes/btswinvista-md.md)]， [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]，或[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]可能会遇到的错误消息**中的服务器错误 / BAM 应用程序**到以下下情况：  
  
-   单击指向不存在的活动实例的相关活动时。  
  
-   在单击同时**保存警报**在以下方案中的按钮：  
  
    -   在创建查询**ActivitySearch**页，然后单击**设置警报**。  
  
    -   你完成警报的字段，然后单击**保存警报**。  
  
    -   单击“上一步”按钮。  
  
    -   你单击**保存警报**再次按钮。  
  
 **可能的原因**  
  
 当在将安全级别设置为低的情况下运行 [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)]（或 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]）和 Internet Explorer 7（或 Internet Explorer 8）时会产生错误，将以较低的权限执行 Web 请求。 为了满足 Windows 的集成安全性，Internet Explorer 传递具有低权限的用户令牌。  
  
 如果在安装 BAM 门户的计算机上使用 Internet Explorer，并在 Internet Explorer 中将安全级别设置为低，则门户将模拟具有低权限令牌的用户。 此令牌不具有向事件日志写入数据的权限。 如果门户遇到错误，它将尝试将其记录到事件日志中并且此尝试将失败，因为用户令牌的权限被降低而不足以访问事件日志。  
  
 **解决方法**  
  
 如果需要从本地计算机上进行浏览，应将 http://localhost 添加到可信站点中。  
  
#### <a name="to-add-localhost-to-the-list-of-trusted-sites"></a>将 localhost 添加到可信站点列表  
  
1.  在 Internet Explorer 中，单击**工具**，然后单击**Internet 选项**。  
  
2.  单击**安全**选项卡上，并依次**受信任的站点**中**选择要查看或更改安全设置的区域**窗口。  
  
3.  单击**站点**按钮。  
  
4.  在**向区域添加此网站**文本框中，键入**http://localhost**。 如果**要求服务器验证 (https:) 此区域中的所有站点**复选框处于选中状态，请清除它，然后单击**添加**按钮。 站点、 http://localhost，将出现在**网站**列表。  
  
5.  如有必要，还原**要求服务器验证 (https:) 此区域中的所有站点**到其原始状态的复选框。  
  
6.  单击**关闭**按钮，，然后单击**确定**。  
  
## <a name="bam-portal-aggregations-do-not-populate-existing-data-when-using-an-ip-address-as-a-url-in-internet-explorer-7"></a>在 Internet Explorer 7 中将 IP 地址用作 URL 时，BAM 门户聚合不填充现有数据  
 **问题**  
  
 使用 IP 地址作为带 Internet Explorer 7 或 Internet Explorer 8 的 URL 时和[!INCLUDE[btsWinVista](../includes/btswinvista-md.md)]， [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]，或[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]查看 BAM 门户，聚合显示以下消息:"没有详细信息。 The query could not be processed."  
  
 **可能的原因**  
  
 在 Internet Explorer 7 或 Internet Explorer 8 中的默认安全设置阻止对站点使用 IPv4 和 IPv6 地址作为 Url 的访问。  
  
 **解决方法**  
  
 将站点地址添加到受信任的站点列表中，即可跨域访问数据源。  
  
#### <a name="to-add-the-ip-address-to-the-trusted-sites-list"></a>将 IP 地址添加到受信任的站点列表中  
  
1.  在 Internet Explorer 中，单击**工具**，然后单击**Internet 选项**。  
  
2.  单击**安全**选项卡上，并依次**受信任的站点**安全区域。  
  
3.  单击**站点**按钮。  
  
4.  在**向区域添加此网站**，键入 BAM 门户的 IP 地址，然后单击**添加**。  
  
5.  单击 **“关闭”**，然后单击 **“确定”**。  
  
#### <a name="to-enable-access-to-data-sources-across-domains"></a>启用跨域数据源访问  
  
1.  在 Internet Explorer 中，单击**工具**，然后单击**Internet 选项**。  
  
2.  单击**安全**选项卡上，并依次**受信任的站点**安全区域。  
  
3.  单击**自定义级别**按钮为你向下滚动到**杂项**节点**设置**树。  
  
4.  在**跨域访问数据源**节点，单击**启用单选**按钮，，然后单击**确定**。  
  
## <a name="bmexe-does-not-run-in-powershell"></a>BM.exe 不在 PowerShell 中运行  
 **问题**  
  
 在 PowerShell 中运行时，以下命名引发错误。  
  
```  
bm.exe get-config -FileName:config.xml  
```  
  
 **可能的原因**  
  
 PowerShell 找不到的.exe 和配置文件的路径。  
  
 **解决方法**  
  
 在 PowerShell 中使用 bm.exe，如果指定.exe 和配置文件的完整路径。 例如：`bm.exe get-config -FileName:config.xml`应指定为`“%BizTalkPathTracking%”\bm.exe get-config -FileName:”%InstallDir%”\Tracking\config.xml`。  
  
## <a name="see-also"></a>另请参阅  
 [规划 BAM 门户](../core/planning-for-the-bam-portal.md)