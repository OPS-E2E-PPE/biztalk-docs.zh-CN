---
title: 使用 JD Edwards OneWorld 系统 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5346aa04-ebd7-4545-9062-b349fd73b7f1
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0fb7bdef551f0ceb66e8eea5ea1fe073bd0bca72
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399926"
---
# <a name="using-a-jd-edwards-oneworld-system"></a>使用 JD Edwards OneWorld 系统
JD Edwards OneWorld 系统是从可访问[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]系统通过使用 JD Edwards OneWorld 适配器。 此适配器是 Microsoft 提供的与 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配合使用的一组八个业务线 (LOB) 适配器之一。  
  
 JD Edwards OneWorld 实验室工作分为两个部分。 第一个实验室 (实验室 1)，可使用 JD Edwards OneWorld 系统，而无需[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]或任何 Microsoft 产品。 您将使用 JD Edwards OneWorld 客户端工具连接到 JD Edwards OneWorld 数据库并找到基于地址的特定记录。  
  
 在第二个实验室 (实验室 2) 中，将创建 BizTalk 项目和业务流程。 创建应用程序后，会将其部署，并使用它来通过使用 JD Edwards OneWorld 适配器连接到 JD Edwards OneWorld 系统。 目标是通过使用适配器通过 BizTalk 应用程序访问数据。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行此实验室的过程，需要安装 JD Edwards OneWorld 客户端软件，且其最新的更新。 若要使用任何客户端软件工具将需要 JD Edwards OneWorld 数据库、 网络连接到该数据库，并在该系统上的用户帐户。 不需要[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]完成此实验。  
  
## <a name="lab-1---using-a-jd-edwards-oneworld-system"></a>实验室 1-使用 JD Edwards OneWorld 系统  
 在此实验室中，你将使用 JD Edwards OneWorld 系统而无需使用的任何组件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 目标是测试与 JD Edwards OneWorld 的连接，以确保第二个实验室可以正常工作。 将使用 JD Edwards OneWorld SQL Plus 工具创建和操作 JD Edwards OneWorld 数据库中的数据表。  
  
## <a name="procedures-for-lab-1---using-a-jd-edwards-oneworld-system"></a>实验室 1-使用 JD Edwards OneWorld 系统的过程  
  
#### <a name="to-log-on-to-jd-edwards-oneworld-by-using-a-browser"></a>若要使用浏览器登录到 JD Edwards OneWorld  
  
-   通过单击 JD Edwards OneWorld 图标登录到 JD Edwards OneWorld 系统。 输入你**用户 ID**，**密码**，并**环境**，然后单击**确定**。  
  
     ![](../core/media/f04db2ef-d587-4357-b9e8-c96319886e97.gif "f04db2ef-d587-4357-b9e8-c96319886e97")  
  
#### <a name="to-locate-and-view-jd-edwards-oneworld-data"></a>若要查找和查看 JD Edwards OneWorld 数据  
  
1.  成功登录后，您在**JD Edwards OneWorld Explorer**。  
  
     ![](../core/media/14e8c206-7e38-48f8-9108-e32a7ac9a740.gif "14e8c206-7e38-48f8-9108-e32a7ac9a740")  
  
2.  展开**主目录**，然后**Foundation 系统**，然后**通讯簿**，然后**每天处理**。  
  
     ![](../core/media/1f742221-00e5-4697-95ff-64aa63ed567a.gif "1f742221-00e5-4697-95ff-64aa63ed567a")  
  
3.  在右侧窗口中，双击**Address Book Revisions**。  
  
     ![](../core/media/a6d4e871-9c9c-4bc0-9c4f-4bdfd7cc5031.gif "a6d4e871-9c9c-4bc0-9c4f-4bdfd7cc5031")  
  
4.  有关**Alpha 名称**，输入`Ga`，选择**显示地址**复选框，然后依次**查找**工具栏上。  
  
     ![](../core/media/2f58413f-41a9-4ed9-ba5c-1d6d59eafb01.gif "2f58413f-41a9-4ed9-ba5c-1d6d59eafb01")  
  
     在中**Address Book Revisions-[Work With Addresses]** 对话框中，两条记录显示为一个搜索结果。  
  
     ![](../core/media/9284df4e-ca9b-48ab-b2bf-a90d765d4a05.gif "9284df4e-ca9b-48ab-b2bf-a90d765d4a05")  
  
     查找数据的一种替代方法是清除**Alpha 名称**字段中，单击上方的文本框中**地址号码**列中，并输入`500`。 单击**查找**上工具栏以显示搜索结果。  
  
     ![](../core/media/a88bd867-9a16-416a-a43e-cdfcc65fc670.gif "a88bd867-9a16-416a-a43e-cdfcc65fc670")  
  
     在实验室 2 中，将使用 JD Edwards OneWorld 适配器来检索的信息说明**地址号码**的`500`。  
  
5.  上**文件**菜单上，单击**退出**以退出 JE Edwards OneWorld 客户端会话。  
  
## <a name="summary"></a>总结  
 在此实验中，您将使用 JD Edwards OneWorld 客户端工具登录到 JD Edwards OneWorld 系统。 连接之后，您搜索特定的数据，并查看返回的数据记录。