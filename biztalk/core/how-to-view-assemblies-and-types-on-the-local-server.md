---
title: "如何查看本地服务器上的程序集和类型 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6ddf6f60-9fef-4997-8b42-24eefd7ab0d1
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37c0f49559de7c4b1a13982578478cf249520479
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-view-assemblies-and-types-on-the-local-server"></a>如何查看本地服务器上的程序集和类型
您可以使用 BizTalk 程序集查看器来查看本地服务器上安装的所有 BizTalk 程序集和类型。  
  
### <a name="to-view-all-biztalk-server-assemblies-installed-in-the-gac"></a>查看 GAC 中安装的所有 BizTalk Server 程序集  
  
-   若要打开 BizTalk 程序集查看器，请双击**我的电脑**，然后双击**BizTalk Server 程序集**。  
  
     此时将显示在计算机上的全局程序集缓存 (GAC) 中安装的所有 BizTalk 程序集。  
  
     ![](../core/media/ebiz-deply-asblyvieweropenpage.gif "ebiz_deply_asblyvieweropenpage")  
程序集查看器打开页  
  
### <a name="to-view-types-attributes-and-references-for-a-biztalk-assembly"></a>查看 BizTalk 程序集的类型、属性和引用  
  
1.  若要打开 BizTalk 程序集查看器，请双击**我的电脑**，然后双击**BizTalk Server 程序集**。  
  
2.  双击适当的程序集。  
  
     BizTalk 程序集显示在右窗格中。 属性和类型显示在左窗格中。  
  
     你还可以导航到安装位置的程序集通过单击**Codebase**左上角的任务窗格中的部分中的链接。 （当 Windows 资源管理器处于文件夹视图时无法看到此链接，因为任务窗格被文件夹列表代替。）  
  
### <a name="to-view-the-contents-of-a-type-in-a-biztalk-assembly"></a>查看 BizTalk 程序集中某一类型的内容  
  
1.  若要打开 BizTalk 程序集查看器，请双击**我的电脑**，然后双击**BizTalk Server 程序集**。  
  
2.  双击适当的程序集。  
  
3.  在右窗格中，双击适当的类型。  
  
     **类型内容查看器**窗口将打开并显示的 XML 定义。  
  
### <a name="to-add-a-biztalk-assembly-in-the-gac"></a>在 GAC 中添加 BizTalk 程序集  
  
1.  若要打开 BizTalk 程序集查看器，请双击**我的电脑**，然后双击**BizTalk Server 程序集**。  
  
2.  使用 Windows 资源管理器浏览到您要在 GAC 中添加的程序集。  
  
3.  将该程序集拖放到 BizTalk 程序集查看器中。  
  
     BizTalk 程序集查看器只接受 BizTalk Server 程序集。 如果在查看器中放入非 BizTalk 程序集，该程序集将被忽略。  
  
### <a name="to-remove-a-biztalk-assembly-from-the-gac"></a>从 GAC 中删除 BizTalk 程序集  
  
1.  若要打开 BizTalk 程序集查看器，请双击**我的电脑**，然后双击**BizTalk Server 程序集**。  
  
2.  右键单击你想要从 GAC，并单击删除程序的集**删除**。  
  
### <a name="to-search-for-a-type-in-all-biztalk-assemblies"></a>在所有 BizTalk 程序集中搜索类型  
  
1.  若要打开 BizTalk 程序集查看器，请双击**我的电脑**，然后双击**BizTalk Server 程序集**。  
  
2.  从菜单栏中，单击**Biz 通信服务器搜索**图标。  
  
3.  在搜索窗口中，指定该类型包在**查找类型**下拉列表。  
  
4.  在**在 BizTalk Server 程序集中查找**下拉列表中，选择要搜索的程序集。  
  
5.  若要缩小您的搜索范围，使之只包括指定类型引用的类型，请执行以下操作：  
  
    1.  单击**高级搜索条件**链接。  
  
    2.  在**其引用的**下拉列表中，选择的类型。  
  
    3.  单击 **“搜索”**。  
  
         指定的类型显示在搜索结果中。  
  
         ![](../core/media/ebiz-depl-asblyviewtypes.gif "ebiz_depl_asblyviewtypes")  
BizTalk 程序集类型  
  
## <a name="see-also"></a>另请参阅  
 [查看具有 BizTalk 程序集查看器的程序集](../core/viewing-assemblies-with-the-biztalk-assembly-viewer.md)