---
title: "如何测试组件接口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- testing component interfaces
- component interfaces, testing
ms.assetid: d637f76d-170d-4543-a2b2-a4ac4001386b
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be50521e5c4421d8ac8902bcf7a414d734c3b9f8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-test-component-interfaces"></a>如何测试组件接口
Microsoft BizTalk Adapter for PeopleSoft Enterprise 使用 PeopleSoft 元数据和组件接口；因此，它可以处理新增或改进过的组件接口。 除假设组件接口符合逻辑并且有效之外，该适配器不对组件接口进行任何其他假设。 因此，每个组件接口在用作适配器的来源之前都必须进行测试。  
  
 如果用户或 PeopleSoft 软件升级对底层应用程序进行了任何更改，并且这些更改使得某个组件接口变为无效，那么在适配器使用组件接口之前，用户必须首先修复无效的接口。  
  
### <a name="to-test-a-component-interface"></a>测试组件接口  
  
1.  在应用程序设计器上**工具**菜单上，单击**测试组件接口**。  
  
     ![](../core/media/psadapter-54-ps-testcompinterface1.gif "PSAdapter_54_PS_TestCompInterface1")  
  
2.  在**组件接口测试人员**对话框框中，通过使用以下方法之一来测试该组件接口。 在您完成更改工作之后，请右键单击窗格中最顶部的一项。  
  
    > [!NOTE]
    >  如果需要，请单击对话框使其成为前台窗口。  
  
    -   若要测试使用查找方法该组件接口，请单击**查找**。  
  
         **组件接口测试器-查找结果**对话框随即打开，显示基础组件的可能的所有项。 如果项数超过 300，会显示一条消息。  
  
         a. 在左窗格中**查找结果**对话框中，选择一个字段。  
  
         b. 若要显示该特定字段的相关数据，请单击**获取的所选**。  
  
         将出现以下屏幕。  
  
         ![](../core/media/psadapter-55-ps-testcompinterface2.gif "PSAdapter_55_PS_TestCompInterface2")  
  
         如果安全设置允许，可以更改各个字段中的值。  
  
         将打开以下对话框。  
  
         ![](../core/media/psadapter-56-ps-testcompinterface3.gif "PSAdapter_56_PS_TestCompInterface3")  
  
    -   若要测试组件接口使用`Get`方法：  
  
         a. 输入现有密钥。  
  
         b. 单击**获取现有**。  
  
         这会返回您输入的键的已公开属性。  
  
         你可以更改值，如果**更新访问权限**指定。  
  
         或者，你可以测试使用`Create`方法。  
  
         ![](../core/media/psadapter-57-ps-testcompinterface4.gif "PSAdapter_57_PS_TestCompInterface4")  
  
    -   若要测试组件接口使用`Create`方法：  
  
         a. 输入所有所需的密钥值。  
  
         b. 单击**创建新**。  
  
         在输入中的有效值**创建密钥**，与默认数据就地展开表名后，此时将打开显示 JOBCODE 数据窗格。  
  
         现在，可以更改字段。  
  
         ![](../core/media/psadapter-58-ps-testcompinterface5.gif "PSAdapter_58_PS_TestCompInterface5")  
  
         将针对组件的底层业务逻辑对更改进行验证。  
  
3.  若要保存所做的更改，请单击**保存**图标。  
  
     用来创建记录的键可以与 Get 方法一起使用以查看数据。 可以在 PeopleSoft Component 中查看添加的数据，如下例所示。  
  
     ![](../core/media/psadapter-59-ps-testcompinterface6.gif "PSAdapter_59_PS_TestCompInterface6")  
  
     **生效日期**是默认值之一。  
  
## <a name="see-also"></a>另请参阅  
 [附录 a： 组件接口方法](../core/appendix-a-component-interface-methods.md)   
 [附录 c： 使用组件接口](../core/appendix-c-using-component-interfaces.md)