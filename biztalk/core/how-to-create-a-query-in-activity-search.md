---
title: 如何在活动搜索中创建查询 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Query Builder [BAM portal], creating queries
- queries [BAM], saving
- queries [BAM], creating
- queries [BAM], executing
- Query Builder [BAM portal], executing queries
- Query Builder [BAM portal], opening queries
- Query Builder [BAM portal], saving queries
- queries [BAM], opening
ms.assetid: 7940e47d-10e4-4eb1-b4e6-a8b98461e3a8
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3fd89ec71319a70c0330ebef80c7c8165cacf6c2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989742"
---
# <a name="how-to-create-a-query-in-activity-search"></a>如何在活动搜索中创建查询
业务最终用户以及其他需要接收有关其业务的事件和状态通知的用户可以使用查询来创建活动搜索，警报将基于这些活动搜索。  
  
## <a name="prerequisites"></a>必要條件  
 必须具有已部署的视图。  
  
### <a name="to-open-a-query"></a>打开查询  
  
1. 单击**启动**，依次指向**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BAM 门户网站**。  
  
2. 在中**我的视图**帧的门户中，单击现有视图，以扩展到该视图的可用菜单。  
  
3. 单击**活动搜索**以展开的活动可用于该视图的列表。  
  
4. 在列表中单击某个活动。 这将加载所选活动的“活动搜索”页。  
  
5. 在内容框架中，顶部的页上，单击**浏览**按钮以打开**选择文件**对话框。  
  
6. 浏览至先前保存查询的文件夹。  
  
7. 单击保存查询。  
  
8. 单击**打开**按钮。 这将加载到左侧的文本框中的查询路径**浏览**按钮。 您还可以在文本框中直接键入查询的路径。  
  
9. 单击**打开查询**右侧的按钮**浏览**按钮。  
  
### <a name="to-construct-a-query"></a>构造查询  
  
1. 单击**启动**，依次指向**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BAM 门户网站**。  
  
2. 在中**我的视图**目前有一系列门户的框架配置视图。 在每个视图下，有三个可从该视图执行的任务。 如果视图当前是折叠的，请单击现有的视图，展开任务列表。  
  
3. 单击**活动搜索**以展开的活动可用于该视图的列表。  
  
4. 在列表中单击某个活动。 这将加载所选活动的“活动搜索”页。  
  
5. 在内容框架中**查询**框中，选择从一个字段**业务数据**下拉列表，用于在查询中的比较。  
  
6. 从**运算符**下拉列表中，选择要使用的比较运算符。  
  
7. 在中**值**框中，输入要比较的值。 您只能输入适合于要进行比较的字段的值。 （如果业务数据项是日期字段，则比较数据为格式适合您的区域性设置的日期或日期时间。）  
  
8. 如果你有更多子句将添加到查询，请单击**添加**按钮右侧的查询框。 这将为下一个子句添加一个新行。 您可以选择是使用 AND 还是使用 OR 来联接子句。  
  
   > [!NOTE]
   >  您无法对子句进行分组以构成更复杂的查询。 查询是一组由 AND 或 OR 运算符联接的简单子句。  
  
   > [!NOTE]
   >  如果您在这些步骤中单击后退按钮，并收到"警告： 网页已过期，"您可以按 F5 重新获得原始内容。 可能需要多次按 F5。  
  
9. 在列选择器中选择的数据或从里程碑**可用的数据和里程碑**查询要作为数据返回的列表框。 您可以选择多个项，方法是按下 SHIFT 键并单击要返回的组中的第一个和最后一个项。 还可以通过按下 CTRL 键并选择要返回的项，从列表中选择多个项。  
  
10. 使用**>>** 按钮，将移动到所选的项目**要显示的项**列表框。 可以通过选择它们并使用从此列表中删除项**<<** 按钮以将它们移回数据和里程碑列表框。  
  
11. 选择了查询要返回的所有项后，可以重排结果，确定列显示的顺序。 若要将列移到返回的数据集的第一个位置，选择通过单击它并单击**移**按钮，直至它位于项列表的顶部。 同样，若要将项移至更高版本中返回的数据集的位置，选择项的单击它，然后单击**下移**按钮，直至它位于希望其显示的位置。  
  
### <a name="to-save-a-query"></a>保存查询  
  
1.  在内容框架中，顶部的页上，单击**保存查询**按钮以打开**保存文件**对话框。  
  
2.  上**文件下载**对话框中，单击**保存**按钮。  
  
3.  浏览至要保存查询的位置。  
  
4.  可以接受为查询提供的默认名称，也可以输入中的新名称**文件名**文本框。  
  
5.  单击**保存**按钮。  
  
### <a name="to-execute-a-query"></a>执行查询  
  
1. 单击**启动**，依次指向**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BAM 门户网站**。  
  
2. 在中**我的视图**帧的门户中，单击现有视图，以扩展到该视图的可用菜单。  
  
3. 单击**活动搜索**以展开的活动可用于该视图的列表。  
  
4. 在列表中单击某个活动。 这将加载所选活动的“活动搜索”页。  
  
5. 打开现有查询，或构建一个新的查询。  
  
6. 在门户的内容框架中，单击**执行查询**按钮。  
  
## <a name="see-also"></a>请参阅  
 [BAM 门户中的活动搜索](../core/activity-searches-in-the-bam-portal.md)