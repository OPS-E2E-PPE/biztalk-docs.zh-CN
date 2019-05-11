---
title: 运行 SQL 适配器示例 |Microsoft Docs
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
ms.openlocfilehash: 7208878da8a2d88b89d1a9ed6a23ac6aaaa5e9a1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65268805"
---
# <a name="running-the-sql-adapter-sample"></a>运行 SQL 适配器示例
SQL 适配器示例使用路线接入点示例随附的 Windows 窗体测试客户端应用程序。  
  
 **若要运行 SQL 适配器示例**  
  
1. 如果尚未运行 GlobalBank.ESB 应用程序，使用 Microsoft BizTalk 管理控制台来启动它。  
  
2. 在 Windows 资源管理器中打开文件夹 \Source\Samples\Itinerary\Source\ESB。安装位置的 Itinerary.Test[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]示例，并启动名为 Esb.Itinerary.Test.exe 应用程序。  
  
3. 清除**使用 WCF 服务**复选框，以便可以使用客户端的路线。  
  
4. 选择**两种方式服务**选项  
  
5. 单击**负载路线**按钮，并选择其中一个位于文件夹 \Source\Samples\SqlAdapter \Itineraries 示例路线。  
  
6. 单击**LoadMessage**按钮，并在文件夹 \Source\Samples\SqlAdapter \Test 选择 OrderDoc.xml 示例消息。  
  
7. 单击**SubmitRequest**按钮以将请求发送到路线接入点服务。  
  
8. 请确保 GlobalBankESB 数据库的 Product 表中插入一行。  
  
   有关 SQL 适配器示例工作原理的信息，请参阅[SQL 适配器示例的工作原理](../esb-toolkit/how-the-sql-adapter-sample-works.md)。