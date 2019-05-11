---
title: 在 PeopleSoft 中生成 XML 或架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- generating schemas
- schemas, generating
- generating XML
- XML, generating
ms.assetid: adfe2936-0dc2-42d2-b26a-718f8cc57eff
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3046a6cb3dc90db69d7d113bf08b92d8c4606bab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387748"
---
# <a name="generating-xml-or-schema-in-peoplesoft"></a>在 PeopleSoft 中生成 XML 或架构
以下过程介绍如何使用 PeopleSoft Enterprise 来创建一个 XML 文件和触发 PeopleSoft 事件。 若要执行此操作，则更改 PeopleSoft 环境中的某些内容。 此更改将激活发送到要监视您的业务流程中设置的文件文件夹的 XML 文件。 更高版本，在 BizTalk Server 中，您导入 XML 并生成架构。  
  
> [!NOTE]
>  对位置值所做的任何更改时将位置与 MSEXTERNAL 节点相关联，生成 XML 文档 — 触发事件。 登记并启动后您的业务流程，可以通过 PeopleSoft 屏幕到 LOCATION 屏幕中进行导航。 如果对位置值进行更改并保存所做的更改时，相应 XML 将出现在 \out 目录中。  
  
### <a name="to-generate-xml-or-schema-in-peoplesoft"></a>若要在 PeopleSoft 中生成 XML 或架构  
  
1. 在 PeopleSoft 应用程序，指向**设置财务**，依次指向**供应链**，指向**常见定义**，指向**位置**，然后选择**位置**。  
  
2. 上**位置**屏幕上，输入以下信息：  
  
   - **设置 ID:** 输入**共享**。  
  
   - **位置代码：** 输入代码开头的`WKLOC`。  
  
     ![](../core/media/psadapter-18-task-sharesearch.gif "PSAdapter_18_Task_ShareSearch")  
  
3. 单击**搜索**，然后单击**正确历史记录**若要将屏幕置于**编辑**模式。  
  
    ![](../core/media/psadapter-19-task-correcthistory.gif "PSAdapter_19_Task_CorrectHistory")  
  
4. 请在屏幕上的字段进行的更改，然后依次**保存**。  
  
5. 指向**PeopleTools**，依次指向**Integration Broker**，指向**监视器**，然后选择**监视器消息**。  
  
    ![](../core/media/psadapter-20-task-monitormessage.gif "PSAdapter_20_Task_MonitorMessage")  
  
6. 请确保**通道类型**是**消息实例**，然后单击**刷新**。  
  
7. 在中**完成**列中，单击的数字。  
  
8. 滚动到列表的底部，单击**详细信息**链接**LOCATION_SYNC**消息。  
  
    ![](../core/media/psadapter-21-task-detailslink.gif "PSAdapter_21_Task_DetailsLink")  
  
9. 单击**查看 XML**上**MSEXTERNAL**节点。  
  
     ![](../core/media/psadapter-22-task-viewxml.gif "PSAdapter_22_Task_ViewXML")  
  
     复制并粘贴到可以访问由 BizTalk Server 项目的文件的 XML 内容。  
  
     ![](../core/media/psadapter-23-task-xmlresult.gif "PSAdapter_23_Task_XMLResult")  
  
10. 请记住文件的位置; 在 BizTalk Server 中引用它。  
  
## <a name="see-also"></a>请参阅  
 [附录 b:使用 PeopleSoft 应用程序](../core/appendix-b-using-the-peoplesoft-application.md)