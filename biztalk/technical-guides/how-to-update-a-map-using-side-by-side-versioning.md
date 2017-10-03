---
title: "如何更新使用的并行版本控制的映射 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7b0e377f-92ab-483e-9f3c-222c7b5ac0b1
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d463823a7038e1ead7e2de323da97eda372db76
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-update-a-map-using-side-by-side-versioning"></a>如何更新使用的并行版本控制的映射
某些 BizTalk 项目，比如地图，选择通过完全限定的强名称 (FQSN)，在这种情况下的绑定包括使用的版本。 这允许两个或多个图并排放置在共存[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 因此，可以发送端口属性中选择其中一个接收位置属性中的入站的映射或出站映射映射。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。  
  
### <a name="to-add-a-second-map-side-by-side-to-an-existing-map"></a>若要将第二个图并排显示添加到现有代码图  
  
1.  打开 Visual Studio，然后打开包含映射的项目。  
  
2.  在程序集中，打开该映射和进行代码更改到映射。  
  
    > [!NOTE]  
    >  如果从业务流程，调用地图和地图引用是硬编码时，你可能需要对业务流程本身进行代码更改。  
  
3.  更改程序集的版本号：  
  
    1.  在解决方案资源管理器，右键单击 BizTalk 项目，然后单击**属性**。  
  
    2.  在**项目设计器**，单击**应用程序**选项卡。  
  
    3.  在右窗格中，单击**程序集信息**。  
  
    4.  在**程序集信息**对话框框中，为指定值**程序集版本**字段以更改程序集版本号。 您应更改仅主要或次要版本号。 主版本号是序列中的第一个数字 (***n***.0.0.0); 的次版本号是序列中的第二个数字 (0。***n ***.0.0)。  
  
    5.  单击**确定**关闭**程序集信息**对话框。  
  
4.  编译的程序集。  
  
5.  将程序集部署到组 （以及所有计算机）。  
  
## <a name="modifying-a-map-to-reflect-updated-version-numbers"></a>修改映射以反映更新版本号  
 使用 脚本 functoid 可以在映射内调用 .NET 程序集。 这样做非常灵活，并可以使开发者能够解决很多不同的自定义映射问题。 它同时也施加在地图上的唯一约束-它必须内部引用的程序集类型名称不仅也正在调用的完整的程序集版本号。 因此，如果更改了映射所调用的程序集版本号，则所有引用该程序集的链接都将中断。  
  
 若要避免此问题，我们建议，如果需要从映射调用程序集，则特定的程序集创建用于保存仅映射功能，并且固定此程序集的程序集版本号。 这样，其他帮助器函数可以更新程序集的版本，而不会中断映射。  
  
 如果映射开发完成后更改了通过该映射引用的某个程序集，则应考虑在映射编辑器外更新该映射文件，使之反映已更新的版本号。  
  
#### <a name="to-modify-a-map-file-to-reflect-updated-version-numbers"></a>若要修改图文件，以反映更新的版本的数字  
  
1.  使用**启动**菜单上，打开**记事本**。  
  
2.  在**记事本**上**文件**菜单上，单击**打开**。 在**打开**对话框中，选择代码图文件您想要修改，然后单击**打开**。  
  
3.  在 **“编辑”** 菜单中，单击 **“查找”**。 在**查找**对话框框中，输入**程序集 =**，然后单击**查找下一个**。  
  
4.  如果存在对外部程序集的脚本引用，则记事本应该找到一个类似如下所示的 XML 元素：  
  
    ```  
    <Script Language="ExternalAssembly" Assembly="Contoso.Scripts, Version=2.0.0.0, Culture=neutral, PublicKeyToken=  
    <token>  
    " Class="Contoso.Scripts" Function="CalculateValue" AssemblyPath="Contoso.Scripts.dll"/>  
    ```  
  
5.  更新版本号。 如果有多个实例，使用**替换**上**编辑**菜单。  
  
6.  保存该文件。  
  
    > [!NOTE]  
    >  现在即可以用映射编辑器打开该映射。