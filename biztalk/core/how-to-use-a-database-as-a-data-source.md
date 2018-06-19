---
title: 如何使用作为数据源的数据库 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rule Composer, data sources
ms.assetid: a68057ed-836f-499f-bb80-f644d81bcfc5
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3a9201ee729288a819a3d527a6ecb4fefd32797
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255709"
---
# <a name="how-to-use-a-database-as-a-data-source"></a>如何将数据库用作数据源
您可以指定数据库作为数据源。 随后，您可从该数据库中选择表或表列，并将其拖至词汇定义或规则上以用作事实。  
  
> [!NOTE]
>  你可以选择将绑定到使用数据库行/表**该组**或**TypedDataTable**通过选择"数据连接"数据库表/行"**数据库绑定类型**性的属性窗口中的下拉列表框**数据库**事实浏览器选项卡。 **数据连接**默认情况下使用绑定。  
  
### <a name="to-specify-a-sql-database-as-a-data-source"></a>指定 SQL 数据库作为数据源  
  
1.  在事实浏览器窗口中，单击**数据库**选项卡。  
  
2.  右键单击**服务器**节点，，然后单击**浏览**。  
  
3.  在下拉列表中选择一个可用的数据库服务器。  
  
4.  选择身份验证类型。 如果您选择 SQL 身份验证，请输入登录名和密码。 输入你的身份验证信息后，单击**确定**。  
  
     ![树浏览器支持的数据库的屏幕截图。] (../core/media/ebiz-dbbrows.gif "ebiz_dbbrows")  
浏览数据库  
  
> [!NOTE]
>  不支持 SQL Server 数据库视图。