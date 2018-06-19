---
title: 添加和删除命名空间在 XML 消息文档 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dbf2f209-13b9-42e0-b0f2-b53ec705e84b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3bb3b28504f92164aca1f66902546f1e04a2290
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289437"
---
# <a name="adding-and-removing-namespaces-in-an-xml-message-document"></a><span data-ttu-id="918fd-102">添加和删除命名空间的 XML 消息文档中</span><span class="sxs-lookup"><span data-stu-id="918fd-102">Adding and Removing Namespaces in an XML Message Document</span></span>
<span data-ttu-id="918fd-103">在此用例，Namespace 组件提供与[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]添加命名空间，或从文档和消息，删除命名空间，如图 1 中所示。</span><span class="sxs-lookup"><span data-stu-id="918fd-103">In this use case, the Namespace component provided with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] adds namespaces to, or removes namespaces from, documents and messages, as illustrated in Figure 1.</span></span> <span data-ttu-id="918fd-104">这可以防止命名空间冲突或错误时的文档使用默认命名空间。</span><span class="sxs-lookup"><span data-stu-id="918fd-104">This prevents namespace clashes or errors arising when documents use default namespaces.</span></span>  
  
 <span data-ttu-id="918fd-105">![添加删除命名空间](../esb-toolkit/media/ch3-addingremovingnamespaces.gif "Ch3 AddingRemovingNamespaces")</span><span class="sxs-lookup"><span data-stu-id="918fd-105">![Adding Removing Namespaces](../esb-toolkit/media/ch3-addingremovingnamespaces.gif "Ch3-AddingRemovingNamespaces")</span></span>  
  
 <span data-ttu-id="918fd-106">**图 1**</span><span class="sxs-lookup"><span data-stu-id="918fd-106">**Figure 1**</span></span>  
  
 <span data-ttu-id="918fd-107">**添加和移除 XML 文档和消息的命名空间**</span><span class="sxs-lookup"><span data-stu-id="918fd-107">**Adding and removing XML document and message namespaces**</span></span>  
  
 <span data-ttu-id="918fd-108">附带 Namespace 组件示例[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]演示此用例。</span><span class="sxs-lookup"><span data-stu-id="918fd-108">The Namespace Component sample included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] demonstrates this use case.</span></span> <span data-ttu-id="918fd-109">它演示如何将组件用于插入和删除文档中的命名空间作为发送和接收过程的一部分。</span><span class="sxs-lookup"><span data-stu-id="918fd-109">It shows how to use the component to inject and remove namespaces in a document as part of the send and the receive process.</span></span>  
  
 <span data-ttu-id="918fd-110">有关详细信息，请参阅[安装和运行 Namespace 组件示例](../esb-toolkit/installing-and-running-the-namespace-component-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="918fd-110">For more information, see [Installing and Running the Namespace Component Sample](../esb-toolkit/installing-and-running-the-namespace-component-sample.md).</span></span>