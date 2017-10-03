---
title: "用于 Oracle E-business Suite 操作的搜索 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2970ddd4-a534-4da4-9bd5-28bb9da4deca
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 797f89b5032d6bcfdb1a4d16f5a83d53d01f1c7f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="search-for-oracle-e-business-suite-operations"></a>用于 Oracle E-business Suite 操作的搜索
你可以使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]搜索 Oracle E-business Suite 中的特定项目。 本主题提供有关如何搜索支持不同的视图和内容信息通配符可以用于搜索 Oracle 项目。 本主题还提供有关如何使用搜索信息[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  


  
> [!NOTE]
>  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]和[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]当您浏览和搜索操作，因此相同的主题中所述两个组件时所显示实质上是相同的接口。  
  
 有关详细信息请参阅[Oracle E-business Suite 适配器将用于 SharePoint](../../adapters-and-accelerators/adapter-oracle-ebs/use-the-oracle-e-business-suite-adapter-with-sharepoint.md)。  
  
## <a name="prerequisites"></a>先决条件  
 你可以搜索目标操作的元数据之前，你必须连接到 Oracle E-business Suite。 有关如何连接到 Oracle 数据库使用时[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，请参阅[连接到 Visual Studio 中 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)。  
  
## <a name="support-for-wildcard-characters"></a>对通配符字符的支持  
 搜索 Oracle E-business Suite 元数据中使用时[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]搜索表达式中支持通配符和转义字符。  
  
|特殊字符|解释|  
|-----------------------|--------------------|  
|_（下划线）|完全匹配一个字符<br /><br /> 例如，A_ 匹配 AB、 AC、 AD。|  
|%（百分比）|匹配零个或多个字符。<br /><br /> 例如，%匹配 A，AB，ABC。|  
|\ （转义）|转义的特殊含义的 %和 _<br /><br /> 例如，A\\_B 匹配 A_B。|  
  
> [!NOTE]
>  转义符是放置在要指示为常规字符而不是通配符，应解释通配符的通配符字符之前的字符。  
  
## <a name="searching-under-different-views"></a>搜索在不同的视图  
 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]和[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]将数据分类到三个视图-基于应用程序的视图、 基于项目的视图和基于架构的视图。 对这些三个视图下的项目进行分类的原因之一是促进基于你要搜索的搜索。 下表描述如何搜索可以异这些视图。  
  
|视图|如何搜索|  
|----------|-------------------|  
|**基于应用程序的视图**|Oracle E-business Suite 应用程序名称的情况下，此视图进行分类。 当你知道哪个应用程序包含你想要使用的项目时，必须使用此视图。<br /><br /> 使用此视图的用户所熟悉的 Oracle 应用程序而识别他们想要使用哪些应用程序。 因此，在此视图下的搜索仅支持即时级别。 例如，如果**基于应用程序的视图**选择节点后，用户可以搜索 Oracle E-business Suite 中的应用程序。 同样，如果**接口表**选择节点后，用户可以搜索接口中的表 Oracle 电子商务应用程序。|  
|**基于项目的视图**|此视图的 Oracle E-business Suite 项目进行分类。 在使用 Oracle E-business Suite 应用程序项目，则用户必须使用此视图，如果他们知道他们想要使用但不能确定哪个应用程序项目所属的 Oracle E-business Suite 项目。<br /><br /> 使用此视图，用户可以搜索特定项目在所有 Oracle E-business Suite 应用程序。 例如，用户可以选择**接口表**节点和使用字符串的搜索`AR%`。 这是将如何执行搜索：<br /><br /> -因为接口表进一步分类下应用程序中，将列出所有应用程序开头 AR。<br />-将列出开头 AR 所有接口表。 这些表可以属于任何 Oracle E-business suite 应用程序。<br /><br /> 在使用 Oracle 数据库项目使用此视图，用户可以搜索特定项目当前的架构与你登录或所有架构下。 例如，如果用户想要使用的架构过程 CREATE_ACCOUNT 但不是接受该过程所属，他们可以选择**所有架构**节点，然后使用字符串的搜索`CREATE%`。|  
|**基于架构的视图**|此视图进行分类的基础的 Oracle 数据库中可用的架构。 当你知道的架构具有你想要使用的项目时，必须使用此视图。<br /><br /> 使用此视图的用户将不熟悉有他们想要使用的项目的架构。 因此，在此视图下的搜索仅支持即时级别。 例如，如果**基于架构的视图**选择节点后，用户可以搜索的 Oracle 数据库中的架构。 同样，如果**表**选择节点后，用户可以搜索 Oracle 电子商务应用程序中的表。|  
  
## <a name="searching-for-operations"></a>搜索操作  
 在其中进行搜索元数据使用 Oracle E-business Suite [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，执行以下步骤。  
  
#### <a name="to-search-metadata-in-oracle-e-business-suite"></a>若要在 Oracle E-business Suite 中搜索元数据  
  
1.  连接到 Oracle E-business Suite 使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 请参阅[连接到 Visual Studio 中 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)有关的说明。  
  
2.  从**选择协定类型**列表中，选择基于是否要搜索入站或出站操作的协定的类型。  
  
3.  在**选择类别**框中，单击要在其下搜索特定项目的类别节点。 例如，若要搜索的 Oracle 应用程序，请单击**基于应用程序的视图**节点。  
  
    > [!NOTE]
    >  若要搜索应用程序可以指定友好名称或应用程序的短名称。 例如，若要搜索**应收帐款**应用程序可以为指定的搜索字符串`Receive%`或`AR`。 AR 是应用程序短名称。  
  
4.  在**类别中的搜索**框中，键入要搜索特定项目搜索表达式。 例如，若要搜索其名称中包含"客户"的 Oracle 应用程序，请键入`%Customer%`。  
  
    > [!NOTE]
    >  区分大小写的搜索字符串。  
  
5.  若要开始搜索，请单击带有右箭头图标的按钮。 完成搜索后**可用类别和操作**框中列出的满足搜索条件的项目。  
  
     下图显示其名称中包含"客户"Oracle 应用程序表。  
  
     ![Oracle （&#45;） 中的搜索元数据Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/media/e6278992-a475-4a35-8371-db862f25a720.gif "e6278992-a475-4a35-8371-db862f25a720")  
  
    > [!NOTE]
    >  若要搜索的并发程序可以指定友好名称或并发程序的实际名称。 例如，若要搜索**客户接口**可以为指定的搜索字符串的并发程序`%Customer Interface%`或`%RACUST%`。 RACUST 是程序的并发的实际名称。  
    >   
    >  此外，搜索结果将始终包含标准的并发程序而不考虑其名称是否与指定的搜索字符串相匹配。  
  
## <a name="see-also"></a>另请参阅  
 [浏览、 搜索和用于 Oracle E-business Suite 操作获取元数据](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)