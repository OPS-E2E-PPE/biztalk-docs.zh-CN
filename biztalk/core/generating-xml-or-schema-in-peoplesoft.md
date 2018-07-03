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
ms.openlocfilehash: fadd89a1e929d672f1b2c8839248d5d03cb27d1c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005630"
---
# <a name="generating-xml-or-schema-in-peoplesoft"></a>在 PeopleSoft 中生成 XML 或架构
以下过程介绍如何使用 PeopleSoft Enterprise 来创建 XML 文件和触发 PeopleSoft 事件。 为此，需更改 PeopleSoft 环境中的某些内容。 此更改将激活发送到文件文件夹（在要监视的业务流程中设置）中的 XML 文件。 随后，在 BizTalk Server 中导入 XML 并生成架构。  
  
> [!NOTE]
>  将位置与 MSEXTERNAL 节点相关联时，对位置值所做的任何更改都会生成一个 XML 文档，从而触发事件。 在登记和启动业务流程之后，可以通过 PeopleSoft 屏幕导航到 LOCATION 屏幕。 如果对位置值进行更改并保存更改，则相应 XML 将出现在 \out 目录中。  
  
### <a name="to-generate-xml-or-schema-in-peoplesoft"></a>若要在 PeopleSoft 中生成 XML 或架构  
  
1. 在 PeopleSoft 应用程序，指向**设置财务**，依次指向**供应链**，指向**常见定义**，指向**位置**，然后选择**位置**。  
  
2. 上**位置**屏幕上，输入以下信息：  
  
   - **组 ID:** 输入**共享**。  
  
   - **位置代码：** 输入开头的代码`WKLOC`。  
  
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
  
     将 XML 的内容复制并粘贴到 BizTalk Server 项目可以访问的文件中。  
  
     ![](../core/media/psadapter-23-task-xmlresult.gif "PSAdapter_23_Task_XMLResult")  
  
10. 请记住该文件的位置；您将在 BizTalk Server 中引用它。  
  
## <a name="see-also"></a>请参阅  
 [附件 B：使用 PeopleSoft 应用程序](../core/appendix-b-using-the-peoplesoft-application.md)