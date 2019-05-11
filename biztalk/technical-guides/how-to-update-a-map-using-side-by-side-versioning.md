---
title: 如何更新使用的并行版本控制的映射 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7b0e377f-92ab-483e-9f3c-222c7b5ac0b1
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ec209d2fb8b2900e27e6699afe722b75c72e0e3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400251"
---
# <a name="how-to-update-a-map-using-side-by-side-versioning"></a>如何更新使用的并行版本控制的映射
某些 BizTalk 项目，如映射，通过完全限定的强名称 (FQSN)，选择在这种情况下的绑定包括所使用的版本。 这允许两个或多个映射以并排放置在共存[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 因此，可以在发送端口属性中选择入站的映射的接收位置属性中或出站映射的映射之一。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。  
  
### <a name="to-add-a-second-map-side-by-side-to-an-existing-map"></a>向现有地图添加第二个图并排显示  
  
1.  打开 Visual Studio，然后打开包含该映射的项目。  
  
2.  在程序集中，打开代码图并进行代码更改到映射。  
  
    > [!NOTE]  
    >  如果从业务流程调用映射和映射引用进行硬编码时，可能需要对业务流程本身进行代码更改。  
  
3.  更改程序集的版本号：  
  
    1.  在解决方案资源管理器，右键单击 BizTalk 项目，然后单击**属性**。  
  
    2.  在中**项目设计器**，单击**应用程序**选项卡。  
  
    3.  在右窗格中，单击**程序集信息**。  
  
    4.  在中**程序集信息**对话框框中，为指定值**程序集版本**字段以更改程序集的版本号。 应更改仅主要或次要版本号。 主版本号是序列中的第一个数字 (***n***.0.0.0); 次版本号是序列中的第二个数字 (0。***n***.0.0)。  
  
    5.  单击**确定**以关闭**程序集信息**对话框。  
  
4.  编译该程序集。  
  
5.  将程序集部署到组 （以及所有计算机）。  
  
## <a name="modifying-a-map-to-reflect-updated-version-numbers"></a>修改映射以反映更新的版本号  
 .NET 程序集可以从调用在映射内使用脚本 functoid。 这提供了大量的灵活性，并使开发者能够解决很多不同的自定义映射问题。 它还规定了在地图上的唯一约束，它必须在内部引用程序集类型名称不仅还正在调用的完整的程序集版本号。 因此，如果更改了映射所调用的程序集的版本号，所有引用程序集的链接将中断。  
  
 若要避免此问题，我们建议，如果需要从映射调用程序集，特定的程序集创建来保存仅映射功能，并且固定此程序集的程序集版本号。 这样一来，其他帮助器函数可以更新而无需中断映射的程序集版本。  
  
 如果通过该映射引用的程序集更改映射开发完成后请考虑更新以反映已更新的版本号在映射编辑器外映射文件。  
  
#### <a name="to-modify-a-map-file-to-reflect-updated-version-numbers"></a>若要修改的映射文件以反映已更新的版本号  
  
1.  使用**启动**菜单中，打开**记事本**。  
  
2.  在中**记事本**，然后在**文件**菜单中，单击**打开**。 在中**开放**对话框中，选择该映射文件您想要修改，然后单击**打开**。  
  
3.  在 **“编辑”** 菜单中，单击 **“查找”**。 在中**查找**对话框框中，输入**程序集 =**，然后单击**查找下一个**。  
  
4.  如果没有对外部程序集的脚本引用，记事本应该找到如下所示的 XML 元素：  
  
    ```  
    <Script Language="ExternalAssembly" Assembly="Contoso.Scripts, Version=2.0.0.0, Culture=neutral, PublicKeyToken=  
    <token>  
    " Class="Contoso.Scripts" Function="CalculateValue" AssemblyPath="Contoso.Scripts.dll"/>  
    ```  
  
5.  更新的版本号。 如果有多个实例，使用**替换为**上**编辑**菜单。  
  
6.  保存该文件。  
  
    > [!NOTE]  
    >  现在可以打开用映射编辑器的映射。