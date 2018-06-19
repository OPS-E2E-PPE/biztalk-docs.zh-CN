---
title: ReceivePortCollection 节点 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ReceivePortCollection node [binding file]
ms.assetid: bddce063-0a32-4b93-88be-f0d06f86e5e5
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 942635c87f6936a51f0b2dc957c15128e753d9b8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268389"
---
# <a name="receiveportcollection-node"></a><span data-ttu-id="16695-102">ReceivePortCollection 节点</span><span class="sxs-lookup"><span data-stu-id="16695-102">ReceivePortCollection Node</span></span>
<span data-ttu-id="16695-103">绑定文件的 ReceivePortCollection 节点是所有 ReceivePort 节点的父节点，ReceivePort 节点包含有关与此绑定文件一起导出的接收端口的特定信息。</span><span class="sxs-lookup"><span data-stu-id="16695-103">The ReceivePortCollection node of a binding file is the parent node for all of the ReceivePort nodes which contain specific information about a receive port that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-receiveportcollection-node"></a><span data-ttu-id="16695-104">ReceivePortCollection 节点中的节点</span><span class="sxs-lookup"><span data-stu-id="16695-104">Nodes in the ReceivePortCollection node</span></span>  
 <span data-ttu-id="16695-105">下表列出了可为绑定文件的此节点设置的属性：</span><span class="sxs-lookup"><span data-stu-id="16695-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="16695-106">**名称**</span><span class="sxs-lookup"><span data-stu-id="16695-106">**Name**</span></span>|<span data-ttu-id="16695-107">**节点类型**</span><span class="sxs-lookup"><span data-stu-id="16695-107">**Node Type**</span></span>|<span data-ttu-id="16695-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="16695-108">**Data Type**</span></span>|<span data-ttu-id="16695-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="16695-109">**Description**</span></span>|<span data-ttu-id="16695-110">**限制**</span><span class="sxs-lookup"><span data-stu-id="16695-110">**Restrictions**</span></span>|<span data-ttu-id="16695-111">**注释**</span><span class="sxs-lookup"><span data-stu-id="16695-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[<span data-ttu-id="16695-112">接收端口</span><span class="sxs-lookup"><span data-stu-id="16695-112">ReceivePort</span></span>](../core/receiveport-receiveportcollection-node.md)|<span data-ttu-id="16695-113">录制</span><span class="sxs-lookup"><span data-stu-id="16695-113">Record</span></span>|<span data-ttu-id="16695-114">ReceivePort (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="16695-114">ReceivePort (ComplexType)</span></span>|<span data-ttu-id="16695-115">指定与绑定文件一起导出的接收端口有关的信息。</span><span class="sxs-lookup"><span data-stu-id="16695-115">Specifies information about a receive port that is exported with the binding file.</span></span>|<span data-ttu-id="16695-116">可选</span><span class="sxs-lookup"><span data-stu-id="16695-116">Not required</span></span>|<span data-ttu-id="16695-117">默认值：无</span><span class="sxs-lookup"><span data-stu-id="16695-117">Default value: none</span></span>|