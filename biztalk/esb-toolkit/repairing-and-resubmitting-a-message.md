---
title: 修复和重新提交一条消息 |Microsoft Docs
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
ms.openlocfilehash: c29e39eaff4cdc1513fea4dd434fda9348d85fcb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65301720"
---
# <a name="repairing-and-resubmitting-a-message"></a>修复和重新提交一条消息
若要修复并重新提交失败的消息，使用 ESB 管理门户的错误页。  
  
### <a name="to-repair-and-resubmit-a-message-for-processing"></a>若要修复并重新提交邮件以进行处理  
  
1.  在上找到所需的错误消息[门户错误页](../esb-toolkit/portal-faults-page.md)ESB 管理门户页。 使用错误页上筛选功能搜索特定的消息。 保留的任何控件为空以检索所有消息。 请注意，筛选非常大的容错数据库上可能需要几秒钟才能显示相应结果。 图 1 说明错误页。  
  
     ![FaultsPage](../esb-toolkit/media/faultspage.gif "FaultsPage")  
  
     **图 1**  
  
     **ESB 管理门户的错误页**  
  
2.  单击所需的错误消息，若要打开的行中的任意位置[门户故障消息查看器](../esb-toolkit/portal-fault-message-viewer.md)页面[错误详细信息视图](../esb-toolkit/fault-details-view.md)。  
  
3.  滚动到错误的详细信息视图到错误消息中包含的消息列表的底部。 图 2 说明了**消息**故障查看器页部分。  
  
     ![消息部分](../esb-toolkit/media/ch8-messagessection.gif "Ch8-MessagesSection")  
  
     **图 2**  
  
     **ESB 管理门户的错误查看器页的消息部分**  
  
4.  单击你想要重新提交该消息的消息标识符。 这将打开中的消息[消息详细信息视图](../esb-toolkit/message-details-view.md)，它显示了各个消息和消息内容的详细信息，如图 3 中所示。  
  
     ![消息查看器](../esb-toolkit/media/ch8-messageviewer.gif "Ch8-MessageViewer")  
  
     **图 3**  
  
     **ESB 管理门户的消息查看器页**  
  
5.  单击**编辑**包含消息内容以切换到编辑模式，然后单击所需的消息内容的文本框下方的链接。 例如，您可能需要更改消息中包含的服务方法调用的参数。 请注意，您必须遵守的本机文档样式 （如 XML 或平面文件格式） 以防止拒绝邮件时重新提交。 图 4 所示**消息的详细信息**消息编辑器页的部分。  
  
     ![消息详细信息](../esb-toolkit/media/ch8-messagedetails.gif "Ch8-MessageDetails")  
  
     **图 4**  
  
     **ESB 管理门户的消息查看器页的消息详细信息部分**  
  
6.  编辑后该消息，消息文本框下的下拉列表中选择重新提交位置。 此列表显示了动态检索可用的终结点的列表。 必须选择一个终结点配置为重新提交终结点。 下列终结点适用于重新提交：  
  
    -   **WCF 的途径**。 此终结点的途径 ESB 路线服务 WCF，仅适用于 XML 文件。 门户网站的 Web.config 文件定义此接入点的 URL。  
  
    -   **SOAP Ramp**。 此终结点是 ESB 路线服务 ASMX 帮手，仅适用于 XML 文件。 门户网站的 Web.config 文件定义此接入点的 URL。  
  
    -   **任何接收位置使用 BizTalk HTTP 适配器**。 此选项才可用的 XML 文件和平面文件。  
  
7.  单击**重新提交**链接以重新提交消息。 一条消息表明**重新提交状态**消息内容文本框的下面会显示。  
  
8.  如有必要，打开[审核日志页](../esb-toolkit/audit-log-page.md)从**管理员**选项卡，确认消息重新提交，如图 5 中所示。  
  
     ![审核日志页小视图](../esb-toolkit/media/ch8-auditlogpagesmallview.gif "Ch8-AuditLogPageSmallView")  
  
     **图 5**  
  
     **ESB 管理门户的审核日志页**