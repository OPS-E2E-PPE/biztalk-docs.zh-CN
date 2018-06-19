---
title: 修复和重新提交一条消息 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ccd720b4-44a2-4c44-bf6e-8cf5e9ded1aa
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e524ffca1b79032dce55f74e195032d14ec1bf9e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295053"
---
# <a name="repairing-and-resubmitting-a-message"></a>修复和重新提交一条消息
修复并重新提交失败的消息，请使用 ESB 管理门户的错误页。  
  
### <a name="to-repair-and-resubmit-a-message-for-processing"></a>若要修复并重新提交邮件以进行处理  
  
1.  在上找到所需的错误消息[门户错误页](../esb-toolkit/portal-faults-page.md)ESB 管理门户页。 在错误页上使用的筛选功能搜索的特定消息。 任何控件留空以检索所有消息。 请注意，筛选非常大的容错数据库上可能需要几秒钟才会显示相应的结果。 图 1 说明错误页。  
  
     ![FaultsPage](../esb-toolkit/media/faultspage.gif "FaultsPage")  
  
     **图 1**  
  
     **ESB 管理门户的错误页上**  
  
2.  若要打开的所需的错误消息的行中单击任一处[门户错误消息查看器](../esb-toolkit/portal-fault-message-viewer.md)页面[错误详细信息视图](../esb-toolkit/fault-details-view.md)。  
  
3.  滚动到底部的错误详细信息视图中的错误消息中包含的消息的列表。 图 2 演示了**消息**错误查看器页面的部分。  
  
     ![消息部分](../esb-toolkit/media/ch8-messagessection.gif "Ch8 MessagesSection")  
  
     **图 2**  
  
     **ESB 管理门户的错误查看器页上的消息部分**  
  
4.  单击你想要重新提交消息的消息标识符。 这将打开中的消息[消息详细信息视图](../esb-toolkit/message-details-view.md)，其中说明了单个消息和消息内容的详细信息，如图 3 中所示。  
  
     ![消息查看器](../esb-toolkit/media/ch8-messageviewer.gif "Ch8 MessageViewer")  
  
     **图 3**  
  
     **ESB 管理门户的消息查看器页上**  
  
5.  单击**编辑**下文本框中，其中包含要切换到编辑模式，然后编辑所需的消息内容的消息内容的链接。 例如，你可能需要更改消息中包含的服务方法调用的参数。 请注意，你必须遵守 （如 XML 或平面文件格式） 的本机文档样式以防止被拒的消息时重新提交。 图 4 显示**消息详细信息**消息编辑器页部分。  
  
     ![消息详细信息](../esb-toolkit/media/ch8-messagedetails.gif "Ch8 MessageDetails")  
  
     **图 4**  
  
     **ESB 管理门户的消息查看器页上的消息详细信息部分**  
  
6.  编辑消息之后, 在消息文本框下的下拉列表中选择重新提交位置。 此列表显示动态检索的可用终结点列表。 你必须选择一个终结点配置为重新提交终结点。 以下终结点是适用于重新提交：  
  
    -   **WCF 入口**。 此终结点是在提升 ESB 路线服务 WCF，仅适用于 XML 文件。 门户网站的 Web.config 文件定义此入口的 URL。  
  
    -   **SOAP 入口**。 此终结点是在提升 ESB 路线服务 ASMX，仅适用于 XML 文件。 门户网站的 Web.config 文件定义此入口的 URL。  
  
    -   **任何接收位置使用 BizTalk HTTP 适配器**。 此选项仅供 XML 文件和平面文件。  
  
7.  单击**重新提交**链接以重新提交消息。 一个消息，表明**重新提交状态**出现在消息内容文本框的下面。  
  
8.  如果需要，请打开[审核日志页](../esb-toolkit/audit-log-page.md)从**管理员**选项卡，确认消息重新提交，如图 5 中所示。  
  
     ![已页面小视图](../esb-toolkit/media/ch8-auditlogpagesmallview.gif "Ch8 AuditLogPageSmallView")  
  
     **图 5**  
  
     **ESB 管理门户的审核日志页上**