---
title: 发布 （创建新消息） 的 MX 消息实例文件 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e7e6cdf4-b9db-42be-a92d-10a7471e2c2d
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4082174428f177905527d0c648b4d7ad000dde36
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="publishing-the-mx-message-instance-file-creating-new-messages"></a>发布 （创建新消息） 的 MX 消息实例文件
**若要发布 MX 消息实例文件：**  
  
1.  转到在上一步中生成的 InfoPath 窗体模板的输出文件夹**...\\< MessageType\>\TemplateDS\InfoPath 窗体模板**。  
  
2.  在 Internet Explorer 中打开**http://localhost/sites/BASSite/New%20SWIFT%20MX%20Messages**。  
  
3.  在新 Swift MX 消息窗口中，单击**上载**。  
  
4.  在上载文档窗口中，单击**浏览**。  
  
5.  在选择文件对话框中，移动到在上一步中生成的 InfoPath 窗体的输出文件夹**...\\< MessageType\>\TemplateDS\InfoPath 窗体模板**。 选择\<MessageType\>.xml pacs.004.001.01.xml，如文件，然后单击**打开**。  
  
6.  在上载文档窗口中，单击**确定**。  
  
7.  新建 SWIFT MX 消息中： \<MessageType\>窗口中的，Namespace 框中，键入 **http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/EnvelopeMX_\<MessageType\>** ，然后单击**确定**.