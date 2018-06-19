---
title: 使用 PeopleSoft 系统 |Microsoft 文档
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
ms.openlocfilehash: c93e025ddb2ccec4b0088c20837a4f307f40aada
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287373"
---
# <a name="using-a-peoplesoft-system"></a>使用 PeopleSoft 系统
使用 PeopleSoft 适配器可以从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 系统访问 PeopleSoft 系统。 此适配器是 Microsoft 提供的与 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配合使用的一组八个业务线 (LOB) 适配器之一。  
  
 PeopleSoft 实验室工作分为两部分。 在第一个实验室（实验室 1）中，您将在不使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 或任何 Microsoft 产品（可能需要使用 Internet Explorer，但您可以使用任何浏览器）的情况下，使用 PeopleSoft 系统。 在此实验室中，您将连接到 PeopleSoft 系统，以找到并修改简单的数据记录。  
  
 在第二个实验室（实验室 2）中，您将创建 BizTalk 项目和业务流程。 创建应用程序之后，将对其进行部署和使用，以使用 PeopleSoft 适配器将其连接到 PeopleSoft 系统。 目标是使用适配器通过 BizTalk 应用程序来访问数据。  
  
## <a name="prerequisites"></a>先决条件  
 为执行此实验室的过程，您需要浏览器和 Internet 连接，以及 PeopleSoft 系统的用户帐户。 您需要知道要浏览的位置，获取对 PeopleSoft 系统的网络访问权限。 无需使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 或其他任何 Microsoft 技术。  
  
## <a name="lab-1---using-a-peoplesoft-system"></a>实验室 1 - 使用 PeopleSoft 系统  
 在此实验室中，您将在不使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的任何组件的情况下，使用 PeopleSoft 系统。 目标是测试与 PeopleSoft 的连接，以确保第二个实验室正常工作。 首先，通过其 Web 界面（允许您使用 Internet Explorer 等浏览器登录）连接到 PeopleSoft 系统。  
  
## <a name="procedures-for-lab-1---using-a-peoplesoft-system"></a>实验室 1 的过程 - 使用 PeopleSoft 系统  
  
#### <a name="to-log-on-to-peoplesoft-by-using-a-browser"></a>使用浏览器登录到 PeopleSoft  
  
-   浏览到 PeopleSoft 登录页，登录到 PeopleSoft 系统。 输入你**用户 ID**和**密码**，然后单击**登录**。  
  
     ![](../core/media/1e3e5c0f-316b-4aa3-946e-3bb3665b0ddb.gif "1e3e5c0f-316b-4aa3-946e-3bb3665b0ddb")  
  
#### <a name="to-locate-and-modify-peoplesoft-data"></a>找到并修改 PeopleSoft 数据  
  
1.  登录成功后，您将转到一个页面，在该页中您可以通过选择布局对看到的内容进行个性化设置。 向下滚动并展开**设置财务/供应链**，单击**通用定义**，单击**位置**，然后单击**位置**试。 这将进入**位置**搜索接口。  
  
     ![](../core/media/62a89cd4-464c-42fd-91cd-60ceeab5b006.gif "62a89cd4-464c-42fd-91cd-60ceeab5b006")  
  
2.  若要开始搜索，设置**SetID**到 **=** ，将其设置**位置代码**到**开头**，输入，然后单击**搜索**。 此时将显示其名称以在 A 开头的城市**搜索结果**接口的部分。  
  
     ![](../core/media/86661144-c666-4d72-9227-9f17df715ba4.gif "86661144-c666-4d72-9227-9f17df715ba4")  
  
3.  单击任一位置以获取其详细信息。 例如，在下图中，用户单击**AUS01**中链接**位置代码**列。  
  
4.  输入一些新的数据的字段之一 (如**地址 2**字段)，然后单击**保存**的左下角。 会将新输入的数据保存到记录中。  
  
     ![](../core/media/b6eb137c-c0b0-4906-8fbd-1bc036069fb0.gif "b6eb137c-c0b0-4906-8fbd-1bc036069fb0")  
  
5.  要验证此更改是否成功，可重复步骤 2 之后的步骤，再次查找同一记录，然后观察对记录所做的更改。  
  
6.  在窗口右上角，单击**注销**以结束 PeopleSoft 会话。  
  
     ![](../core/media/7760b541-5155-453e-a682-4780412f3c13.gif "7760b541-5155-453e-a682-4780412f3c13")  
  
    > [!NOTE]
    >  下一个实验室中为使用 PeopleSoft 适配器检索您修改的位置记录 (AUS01) 的信息提供了说明。  
  
## <a name="summary"></a>摘要  
 在本实验室中，您通过浏览器登录到 PeopleSoft 系统。 连接之后，您搜索了数据，然后对记录的地址字段进行了操作和更新。 提交更改后，您可以在浏览器中查看修改的数据，以验证更改是否正确执行。