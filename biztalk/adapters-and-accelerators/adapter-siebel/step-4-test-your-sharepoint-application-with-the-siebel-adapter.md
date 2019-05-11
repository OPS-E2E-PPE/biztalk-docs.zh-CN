---
title: 步骤 4：使用 Siebel 适配器测试您的 SharePoint 应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ec1392fa-fdc1-42be-b4dc-75a55d8fa400
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 555339a90d51e5fa66f8be397be6af9eeb589f76
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370667"
---
# <a name="step-4-test-your-sharepoint-application-with-the-siebel-adapter"></a>步骤 4：使用 Siebel 适配器测试您的 SharePoint 应用程序
![步骤 4 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")  
  
 **若要完成的时间：** 5 分钟。  
  
 **目标：** 在 SharePoint 站点中添加 Web 部件并创建了应用程序后，必须从 Siebel 系统中检索一些数据来测试应用程序。 本部分将说明了如何使用应用程序从 Siebel 系统中检索数据。  
  
## <a name="prerequisites"></a>先决条件  
 您将会创建包含相应的 Web 部件，以检索业务数据的 Web 部件页。 请参阅[步骤 3:创建 SharePoint 应用程序以从 Siebel 检索数据](../../adapters-and-accelerators/adapter-siebel/step-3-create-a-sharepoint-application-to-retrieve-data-from-siebel.md)。  
  
### <a name="to-test-the-sharepoint-application"></a>若要测试 SharePoint 应用程序  
  
1.  启动 SharePoint 3.0 管理中心。 单击**启动**，依次指向**所有程序**，指向**Microsoft Office Server**，然后单击**SharePoint 3.0 管理中心**.  
  
2.  在左侧的导航窗格中，单击的 SSP 在其下创建应用程序的名称。  
  
3.  在左窗格中，单击**查看所有网站内容**。 在右窗格中，单击**窗体模板**。  
  
4.  在中**窗体类别**列表中，单击**Siebel 帐户**。 创建 Web 部件页时指定此名称。 下图显示了你创建的 Web 部件页。  
  
     ![已完成的 Web 部件页](../../adapters-and-accelerators/adapter-siebel/media/a0bfe7af-0246-4f0b-aa0d-0ee084456003.gif "a0bfe7af-0246-4f0b-aa0d-0ee084456003")  
  
5.  查询帐户业务组件根据搜索字符串。 例如，指定搜索表达式`[Name] LIKE ‘W*’`。 为此，请执行以下操作：  
  
    1.  在中**Account List**部分中的，从第一个列表中，选择**SearchExpression**，然后选择**等于**。  
  
    2.  在文本字段中，键入`[Name] LIKE ‘W*’`。  
  
    3.  单击**检索数据**链接，或按 ENTER。 下图显示了从 Siebel 系统中检索满足搜索条件的记录。  
  
         ![搜索从 Siebel 系统的结果](../../adapters-and-accelerators/adapter-siebel/media/6c4721ac-c7bc-4626-9ee0-55cf322026cf.gif "6c4721ac-c7bc-4626-9ee0-55cf322026cf")  
  
## <a name="see-also"></a>请参阅  
 [教程 1:在 SharePoint 站点上提供来自 Siebel 系统的数据](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md)