---
title: 发布 MX 消息实例文件 （创建新消息） |Microsoft Docs
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
ms.openlocfilehash: 1f6375f61d484903b9359e2d3ab8723e6996d776
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377058"
---
# <a name="publishing-the-mx-message-instance-file-creating-new-messages"></a>发布 MX 消息实例文件 （创建新消息）
**若要发布 MX 消息实例文件：**  

1. 转到上一步中生成的 InfoPath 表单模板的输出文件夹 **...\\< MessageType\>\TemplateDS\InfoPath 窗体模板**。  

2. 在 Internet Explorer 中，打开**http://localhost/sites/BASSite/New%20SWIFT%20MX%20Messages**。  

3. 在新 Swift MX 消息窗口中，单击**上传**。  

4. 在上载文档窗口中，单击**浏览**。  

5. 在选择文件对话框中，转到 InfoPath 窗体上一步中生成的输出文件夹 **...\\< MessageType\>\TemplateDS\InfoPath 窗体模板**。 选择\<MessageType\>.xml pacs.004.001.01.xml，如文件，然后单击**打开**。  

6. 在上载文档窗口中，单击**确定**。  

7. 在新的 SWIFT MX 消息：\<MessageType\>窗口中的，Namespace 框中，键入<strong>http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/EnvelopeMX_\<MessageType\></strong>，然后单击**确定**。
