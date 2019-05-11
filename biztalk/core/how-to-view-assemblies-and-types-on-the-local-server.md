---
title: 如何查看本地服务器上的程序集和类型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6ddf6f60-9fef-4997-8b42-24eefd7ab0d1
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d119fa6672ca5b01470336b4f8749c96459112e0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333075"
---
# <a name="how-to-view-assemblies-and-types-on-the-local-server"></a>如何查看本地服务器上的程序集和类型
可以使用 BizTalk 程序集查看器来检查所有 BizTalk 程序集和本地服务器上安装的类型。  
  
### <a name="to-view-all-biztalk-server-assemblies-installed-in-the-gac"></a>若要查看所有 BizTalk Server 程序集安装到 GAC 中  
  
-   若要打开 BizTalk 程序集查看器，请双击**我的电脑**，然后双击**BizTalk Server 程序集**。  
  
     所有 BizTalk 程序集安装在计算机上的全局程序集缓存 (GAC) 中都显示。  
  
     ![](../core/media/ebiz-deply-asblyvieweropenpage.gif "ebiz_deply_asblyvieweropenpage")  
程序集查看器打开页  
  
### <a name="to-view-types-attributes-and-references-for-a-biztalk-assembly"></a>若要查看 BizTalk 程序集的类型、 属性和引用  
  
1.  若要打开 BizTalk 程序集查看器，请双击**我的电脑**，然后双击**BizTalk Server 程序集**。  
  
2.  双击适当的程序集。  
  
     在右窗格中显示了 BizTalk 程序集类型。 属性和类型显示在左窗格中。  
  
     您还可导航到已安装的程序集的位置通过单击**基本代码**的左上角的任务窗格中的链接。 （在 Windows 资源管理器是在文件夹视图中，因为任务窗格被文件夹列表时无法查看此链接。）  
  
### <a name="to-view-the-contents-of-a-type-in-a-biztalk-assembly"></a>若要查看 BizTalk 程序集中的一种类型的内容  
  
1.  若要打开 BizTalk 程序集查看器，请双击**我的电脑**，然后双击**BizTalk Server 程序集**。  
  
2.  双击适当的程序集。  
  
3.  在右窗格中，双击适当的类型。  
  
     **类型内容查看器**窗口将打开并显示 XML 定义。  
  
### <a name="to-add-a-biztalk-assembly-in-the-gac"></a>若要在 GAC 中添加 BizTalk 程序集  
  
1.  若要打开 BizTalk 程序集查看器，请双击**我的电脑**，然后双击**BizTalk Server 程序集**。  
  
2.  使用 Windows 资源管理器导航到你想要在 GAC 中添加的程序集。  
  
3.  将程序集拖放到 BizTalk 程序集查看器上。  
  
     BizTalk 程序集查看器接受仅 BizTalk Server 程序集。 如果在查看器中删除非 BizTalk 程序集，则忽略它。  
  
### <a name="to-remove-a-biztalk-assembly-from-the-gac"></a>若要从 GAC 中删除 BizTalk 程序集  
  
1.  若要打开 BizTalk 程序集查看器，请双击**我的电脑**，然后双击**BizTalk Server 程序集**。  
  
2.  右键单击你想要从 GAC 和单击删除的程序集**删除**。  
  
### <a name="to-search-for-a-type-in-all-biztalk-assemblies"></a>若要搜索所有 BizTalk 程序集中的类型  
  
1.  若要打开 BizTalk 程序集查看器，请双击**我的电脑**，然后双击**BizTalk Server 程序集**。  
  
2.  从菜单栏中，单击**Biz 通信服务器搜索**图标。  
  
3.  在搜索窗口中，指定在类型**查找类型**下拉列表。  
  
4.  在中**在 BizTalk Server 程序集中查找**下拉列表中，选择要搜索的程序集。  
  
5.  若要缩小搜索范围以包括引用的指定类型的类型，请执行以下操作：  
  
    1.  单击**高级搜索条件**链接。  
  
    2.  在中**引用的**下拉列表中，选择的类型。  
  
    3.  单击 **“搜索”**。  
  
         指定的类型显示在搜索结果中。  
  
         ![](../core/media/ebiz-depl-asblyviewtypes.gif "ebiz_depl_asblyviewtypes")  
BizTalk 程序集类型  
  
## <a name="see-also"></a>请参阅  
 [使用 BizTalk 程序集查看器查看程序集](../core/viewing-assemblies-with-the-biztalk-assembly-viewer.md)