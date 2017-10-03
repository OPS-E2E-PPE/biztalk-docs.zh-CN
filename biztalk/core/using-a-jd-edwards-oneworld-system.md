---
title: "使用博士 Edwards OneWorld 系统 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5346aa04-ebd7-4545-9062-b349fd73b7f1
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 835432e50bce3f347e6f769fb8182ab35fc4f949
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-a-jd-edwards-oneworld-system"></a>使用 JD Edwards OneWorld 系统
可以使用 JD Edwards OneWorld 适配器从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 系统中访问 JD Edwards OneWorld 系统。 此适配器是 Microsoft 提供的与 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配合使用的一组八个业务线 (LOB) 适配器之一。  
  
 JD Edwards OneWorld 实验室工作分为两部分。 第一个实验室（实验室 1）允许您使用 JD Edwards OneWorld 系统，而无需 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 或任何 Microsoft 产品。 您将使用 JD Edwards OneWorld 客户端工具连接到 JD Edwards OneWorld 数据库并根据地址查找特定的记录。  
  
 在第二个实验室（实验室 2）中，您将创建 BizTalk 项目和业务流程。 创建应用程序之后，将对其进行部署和使用，并通过 JD Edwards OneWorld 适配器连接到 JD Edwards OneWorld 系统。 目标是使用适配器通过 BizTalk 应用程序来访问数据。  
  
## <a name="prerequisites"></a>先决条件  
 为执行此实验室的过程，您需要安装 JD Edwards OneWorld 客户端软件及其最新更新。 若要使用任意客户端软件工具，您需要 JD Edwards OneWorld 数据库、到该数据库的网络连接以及该系统上的用户帐户。 不需要 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 即可完成此实验。  
  
## <a name="lab-1---using-a-jd-edwards-oneworld-system"></a>实验室 1 - 使用 JD Edwards OneWorld 系统  
 在此实验室中，您将使用 JD Edwards OneWorld 系统，而无需使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的任何组件。 目标是测试与 JD Edwards OneWorld 的连接，以确保第二个实验室可以正常工作。 您将使用 JD Edwards OneWorld SQL Plus 工具创建并处理 JD Edwards OneWorld 数据库中的数据表。  
  
## <a name="procedures-for-lab-1---using-a-jd-edwards-oneworld-system"></a>实验室 1 的过程 - 使用 JD Edwards OneWorld 系统  
  
#### <a name="to-log-on-to-jd-edwards-oneworld-by-using-a-browser"></a>使用浏览器登录到 JD Edwards OneWorld 的步骤  
  
-   通过单击 JD Edwards OneWorld 图标登录到 JD Edwards OneWorld 系统。 输入你**用户 ID**，**密码**，和**环境**，然后单击**确定**。  
  
     ![](../core/media/f04db2ef-d587-4357-b9e8-c96319886e97.gif "f04db2ef-d587-4357-b9e8-c96319886e97")  
  
#### <a name="to-locate-and-view-jd-edwards-oneworld-data"></a>查找和查看 JD Edwards OneWorld 数据的步骤  
  
1.  成功登录使用户在**博士 Edwards OneWorld 资源管理器**。  
  
     ![](../core/media/14e8c206-7e38-48f8-9108-e32a7ac9a740.gif "14e8c206-7e38-48f8-9108-e32a7ac9a740")  
  
2.  展开**主路径**，然后**Foundation 系统**，然后**通讯簿**，，然后**每天处理**。  
  
     ![](../core/media/1f742221-00e5-4697-95ff-64aa63ed567a.gif "1f742221-00e5-4697-95ff-64aa63ed567a")  
  
3.  在右侧的窗口中，双击**地址簿修订**。  
  
     ![](../core/media/a6d4e871-9c9c-4bc0-9c4f-4bdfd7cc5031.gif "a6d4e871-9c9c-4bc0-9c4f-4bdfd7cc5031")  
  
4.  有关**字母名称**，输入`Ga`，选择**显示地址**复选框，并依次**查找**工具栏上。  
  
     ![](../core/media/2f58413f-41a9-4ed9-ba5c-1d6d59eafb01.gif "2f58413f-41a9-4ed9-ba5c-1d6d59eafb01")  
  
     在**地址簿修订版本-[工作与地址]**对话框中，搜索结果显示两条记录。  
  
     ![](../core/media/9284df4e-ca9b-48ab-b2bf-a90d765d4a05.gif "9284df4e-ca9b-48ab-b2bf-a90d765d4a05")  
  
     查找数据的一种替代方法是清除**字母名称**字段中，在上面的文本框中单击**地址数**列，并输入`500`。 单击**查找**在工具栏上，以显示搜索结果。  
  
     ![](../core/media/a88bd867-9a16-416a-a43e-cdfcc65fc670.gif "a88bd867-9a16-416a-a43e-cdfcc65fc670")  
  
     在实验室 2 中，将使用博士 Edwards OneWorld 适配器若要检索的信息的说明**地址数**的`500`。  
  
5.  上**文件**菜单上，单击**退出**退出 JE Edwards OneWorld 客户端会话。  
  
## <a name="summary"></a>摘要  
 在此实验室中，您使用了用于登录到 JD Edwards OneWorld 系统的 JD Edwards OneWorld 客户端工具。 连接后，您对特定数据进行了搜索并查看了返回的数据记录。