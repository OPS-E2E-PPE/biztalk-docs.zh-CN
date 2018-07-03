---
title: 重新生成实时数据工作簿 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4bd3a3fa-a550-4363-bbc0-2153226509ad
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f6c62686c15c2e0b04576ca3175fb22d52a71922
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987406"
---
# <a name="regenerate-the-live-data-workbook"></a>重新生成实时数据工作簿
在 BAM 实时数据工作簿丢失或损坏时，可使用 BAM 管理实用程序重新生成工作簿。 此过程时，还从升级从早期的 BizTalk Server 版本。
  
 常规步骤如下所示：  
  
-   使用 BAM 管理实用程序从 BAM 数据库中检索 BAM 定义。  
  
-   重新创建数据透视表。 由于 get-defxml 命令完成的 XML 检索仅包含活动和视图，因此必须使用用于 Excel 的 BAM 加载项重新创建数据透视表。  
  
-   重命名数据透视表。 如果从以前的 BizTalk Server 版本进行升级，则可能需要采用此步骤。 在某些版本中，BAM 存储两组 BAM 工作簿的名称： 显示名称和内部名称。 在检索 BAM 定义时，XML 包含工作簿的内部名称。 必须重命名数据透视表，以确保实时数据工作簿可正确地连接到数据库。  
  
-   使用 BAM 管理实用程序重新生成实时数据工作簿。  
  
## <a name="retrieve-the-bam-definition"></a>检索 BAM 定义  
  
1. 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2. 在命令提示符处，导航到以下目录： [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Tracking。  
  
3. 类型： **bm.exe get defxml-FileName:abc.xml**  
  
   > [!NOTE]
   >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
## <a name="recreate-the-pivottable-reports"></a>重新创建数据透视表报表  
  
1. 单击**启动**，依次指向**所有程序**，指向**Microsoft Office**，然后单击**Microsoft Office Excel**。  
  
2. 单击**外接程序**选项卡，然后选择**导入 XML**从**BAM**下拉列表中的**菜单命令**组。  
  
   > [!NOTE]
   >  如果**外接程序**选项卡上不存在，请按照中的说明[步骤 1： 将 BAM 外接程序添加到 Microsoft Office Excel](http://msdn.microsoft.com/library/3400969f-0c54-4a75-979d-ad2f7af86448)若要添加的 BAM 外接程序。  
  
3. 导航到 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Tracking 文件夹，然后选择 abc.xml 文件。  
  
4. 根据您的定义重新创建数据透视表。  
  
5. 保存该工作簿。 若要执行此操作，请单击**文件**菜单，并单击**另存为**和输入文件的名称出现提示时键入 mynewbook.xls。  
  
## <a name="rename-the-pivottable-reports-optional"></a>重命名数据透视表报表 （可选）  

> [!NOTE]
> 此步骤可能仅需要如果从较旧版本的 BizTalk Server 进行升级。 

1. 打开在检索 BAM 定义通过使用记事本时创建的 abc.xml 文件**启动**，再单击**运行**，键入 notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Tracking\abc.xml，，然后单击**确定**。  
  
2. 找到\<标题\>标记下\<BAMDefinition\>\\< 扩展\>\\< OWC\>\\< PivotTableView\> \\< 数据透视表\>\\< PivotView\>\\< 标签\>。 此标记的内容是某个数据透视表的内部名称。 可以通过查找下一步找到的其他数据透视表报表的内部名称\<标题\>标记。 打开**mynewbook.xls**并使用位于重命名数据透视表的名称。  
  
3. 保存已更新的工作簿。    
 
  
## <a name="regenerate-the-bam-live-data-workbook"></a>重新生成 BAM 实时数据工作簿  

> [!NOTE]
>  使用管理权限运行此工具。  


1. 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2. 在命令提示符处，导航到以下目录： [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Tracking。  
  
3. 类型： **bm.exe 重新生成 livedataworkbook-WorkbookName:mynewbook.xls**  
  
## <a name="see-also"></a>请参阅  
 [管理 BAM](../core/managing-bam.md)   
 [BAM 管理实用程序](../core/bam-management-utility.md)   
 [使用 excel 的 BAM 外接程序的要求](../core/requirements-for-using-the-bam-add-in-for-excel.md)   
 [步骤 1： 向 Microsoft Office Excel 的 BAM 外接程序添加](http://msdn.microsoft.com/library/3400969f-0c54-4a75-979d-ad2f7af86448)