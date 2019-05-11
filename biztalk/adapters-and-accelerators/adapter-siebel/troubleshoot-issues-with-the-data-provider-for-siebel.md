---
title: 用于 Siebel 的数据提供程序的问题进行故障排除 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Data Provider for Siebel, troubleshooting
- troubleshooting, Data Provider for Siebel
ms.assetid: 2bfe69a2-d6de-466d-9f36-f11c386c771c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: adeae6cc42aebb1ddae3c3c3e769fdb77984d878
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370435"
---
# <a name="troubleshoot-issues-with-the-data-provider-for-siebel"></a><span data-ttu-id="2e931-102">用于 Siebel 的数据提供程序的问题进行故障排除</span><span class="sxs-lookup"><span data-stu-id="2e931-102">Troubleshoot Issues with the Data Provider for Siebel</span></span>
<span data-ttu-id="2e931-103">本部分讨论如何使用故障排除方法来解决在使用时可能遇到的错误[!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="2e931-103">This section discusses using troubleshooting techniques to resolve errors that you might encounter when using the [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]).</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="2e931-104">已知问题</span><span class="sxs-lookup"><span data-stu-id="2e931-104">Known Issues</span></span>  
  
### <a name="data-provider-for-siebel-may-give-component-datareader-source-380-error"></a><span data-ttu-id="2e931-105">用于 Siebel 的数据提供程序都可能导致"组件 DataReader Source (380)"错误</span><span class="sxs-lookup"><span data-stu-id="2e931-105">Data Provider for Siebel may give "component 'DataReader Source' (380)" error</span></span>  
 <span data-ttu-id="2e931-106">**问题**</span><span class="sxs-lookup"><span data-stu-id="2e931-106">**Problem**</span></span>  
  
 <span data-ttu-id="2e931-107">Siebel 业务组件，对执行 SELECT 查询时[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]都可能导致"组件 DataReader Source (380)"错误。</span><span class="sxs-lookup"><span data-stu-id="2e931-107">While performing a SELECT query on a Siebel business component, the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] may give a "component 'DataReader Source' (380)" error.</span></span>  
  
 <span data-ttu-id="2e931-108">**原因**</span><span class="sxs-lookup"><span data-stu-id="2e931-108">**Cause**</span></span>  
  
 <span data-ttu-id="2e931-109">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]如果收到从 Siebel 系统的参数的值超出了该参数的 maxLength 属性时出现此错误。</span><span class="sxs-lookup"><span data-stu-id="2e931-109">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] gives this error if the value received from the Siebel system for a parameter exceeds the maxLength property for the parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e931-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="2e931-110">See Also</span></span>  
[<span data-ttu-id="2e931-111">Siebel 适配器疑难解答</span><span class="sxs-lookup"><span data-stu-id="2e931-111">Troubleshoot the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)