---
title: 使用 PeopleSoft 系统 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c228ac23-184f-4c08-922b-ba84f5f2c52f
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b7f98086c5e2be4e236a5691e4ff5633ac5f45b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399944"
---
# <a name="using-a-peoplesoft-system"></a>使用 PeopleSoft 系统
使用 PeopleSoft 适配器可以从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 系统访问 PeopleSoft 系统。 此适配器是 Microsoft 提供的与 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配合使用的一组八个业务线 (LOB) 适配器之一。  
  
 PeopleSoft 实验室工作分为两个部分。 第一个实验室 (实验室 1)，可使用 PeopleSoft 系统，而无需[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]或任何 Microsoft 产品 （可能是 Internet Explorer 中，但你可以使用任何浏览器）。 在此实验中，您将连接到 PeopleSoft 系统以找到并修改简单的数据记录。  
  
 在第二个实验室 (实验室 2) 中，将创建 BizTalk 项目和业务流程。 创建应用程序后，会将其部署，并使用它来通过使用 PeopleSoft 适配器连接到 PeopleSoft 系统。 目标是通过使用适配器通过 BizTalk 应用程序访问数据。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行此实验室的过程，需要一个浏览器和 Internet 连接，以及 PeopleSoft 系统上的用户帐户。 您需要知道要浏览到 PeopleSoft 系统 Web 访问的位置。 不需要[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]或任何其他 Microsoft 技术。  
  
## <a name="lab-1---using-a-peoplesoft-system"></a>实验室 1-使用 PeopleSoft 系统  
 在此实验室中，你将使用 PeopleSoft 系统而无需使用的任何组件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 目标是测试与 PeopleSoft 以确保第二个实验室可以正常工作的连接。 最初连接到 PeopleSoft 系统通过其 Web 界面，您可以使用 Internet Explorer 等浏览器登录。  
  
## <a name="procedures-for-lab-1---using-a-peoplesoft-system"></a>实验室 1-使用 PeopleSoft 系统的过程  
  
#### <a name="to-log-on-to-peoplesoft-by-using-a-browser"></a>若要使用浏览器登录到 PeopleSoft  
  
-   通过浏览到 PeopleSoft 登录页登录到 PeopleSoft 系统。 输入你**用户 ID**并**密码**，然后单击**登录**。  
  
     ![](../core/media/1e3e5c0f-316b-4aa3-946e-3bb3665b0ddb.gif "1e3e5c0f-316b-4aa3-946e-3bb3665b0ddb")  
  
#### <a name="to-locate-and-modify-peoplesoft-data"></a>若要找到并修改 PeopleSoft 数据  
  
1.  成功登录后，在页后，可以通过选择其布局，看到的内容进行个性化设置您。 向下滚动并展开**设置财务状况/供应链**，单击**常见定义**，单击**位置**，然后单击**位置**电子邮件了。 这将进入**位置**搜索界面。  
  
     ![](../core/media/62a89cd4-464c-42fd-91cd-60ceeab5b006.gif "62a89cd4-464c-42fd-91cd-60ceeab5b006")  
  
2.  若要开始搜索，请设置**SetID**到 **=** ，将**位置代码**到**开头**，输入  ，然后单击**搜索**。 这将显示的城市名称开头中的一个**搜索结果**接口的部分。  
  
     ![](../core/media/86661144-c666-4d72-9227-9f17df715ba4.gif "86661144-c666-4d72-9227-9f17df715ba4")  
  
3.  单击其中一个要获取其详细信息的位置。 例如，在下图中，用户单击**AUS01**中的链接**位置代码**列。  
  
4.  为一个字段中输入一些新数据 (如**地址 2**字段)，单击**保存**左下角。 这会将新输入的数据保存到记录。  
  
     ![](../core/media/b6eb137c-c0b0-4906-8fbd-1bc036069fb0.gif "b6eb137c-c0b0-4906-8fbd-1bc036069fb0")  
  
5.  若要验证此更改的成功，重复步骤 2 中的过程，再次查找同一记录并观察对记录所做的更改。  
  
6.  在窗口的右上方部分，单击**注销**以结束 PeopleSoft 会话。  
  
     ![](../core/media/7760b541-5155-453e-a682-4780412f3c13.gif "7760b541-5155-453e-a682-4780412f3c13")  
  
    > [!NOTE]
    >  在下一步的实验室中有使用 PeopleSoft 适配器检索您修改的位置记录 (AUS01) 的信息的说明。  
  
## <a name="summary"></a>总结  
 在此实验室中您登录到 PeopleSoft 系统通过浏览器。 连接之后，您搜索了数据，然后操作并更新记录的地址字段。 后提交更改，您可以查看修改后的数据来验证在浏览器中正确执行的更改。