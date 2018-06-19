---
title: 运行 SQL 适配器示例 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 13566d08-7a59-4065-b0d7-19ae2765555e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf04c06a1ef96974912ce3affe278d5a98936325
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294789"
---
# <a name="running-the-sql-adapter-sample"></a>运行 SQL 适配器示例
SQL 适配器示例使用了路线入口示例随附的 Windows 窗体测试客户端应用。  
  
 **若要运行 SQL 适配器示例**  
  
1.  如果 GlobalBank.ESB 应用程序尚未运行，使用 Microsoft BizTalk 管理控制台来启动它。  
  
2.  在 Windows 资源管理器，打开文件夹 \Source\Samples\Itinerary\Source\ESB。你的安装位置的 Itinerary.Test[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]示例，，然后启动指定 Esb.Itinerary.Test.exe 的应用程序。  
  
3.  清除**使用 WCF 服务**复选框，以便可以使用客户端路线。  
  
4.  选择**两个方式服务**选项  
  
5.  单击**负载路线**按钮，，然后选择一个位于文件夹 \Source\Samples\SqlAdapter \Itineraries 示例路线。  
  
6.  单击**LoadMessage**按钮，，然后选择在文件夹 \Source\Samples\SqlAdapter \Test 中的 OrderDoc.xml 示例消息。  
  
7.  单击**SubmitRequest**按钮以将请求发送到路线提升服务。  
  
8.  请确保 GlobalBankESB 数据库的产品表中插入一行。  
  
 有关 SQL 适配器示例的工作原理的信息，请参阅[SQL 适配器示例的工作原理](../esb-toolkit/how-the-sql-adapter-sample-works.md)。