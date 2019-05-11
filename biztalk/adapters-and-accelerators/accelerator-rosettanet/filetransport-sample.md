---
title: FileTransport 示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a32c8cbf-0c17-4237-b2a3-9d21faa13496
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a79759a94b2effd751dd566d62dcdde51395e566
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283716"
---
# <a name="filetransport-sample"></a><span data-ttu-id="7c3cc-102">FileTransport 示例</span><span class="sxs-lookup"><span data-stu-id="7c3cc-102">FileTransport Sample</span></span>
<span data-ttu-id="7c3cc-103">FileTransport 示例演示如何配置 Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]若要使用文件端口而不是 SQL 端口。</span><span class="sxs-lookup"><span data-stu-id="7c3cc-103">The FileTransport sample demonstrates how to configure Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] to use File ports, instead of SQL ports.</span></span> <span data-ttu-id="7c3cc-104">FileTransport 示例使用文件传输协议 (FTP) 来发送和接收消息，而不是 HTTP。</span><span class="sxs-lookup"><span data-stu-id="7c3cc-104">The FileTransport sample uses File Transport Protocol (FTP) to send and receive messages, instead of HTTP.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7c3cc-105">本文档假定您在安装[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]针对内部测试或演示目的。</span><span class="sxs-lookup"><span data-stu-id="7c3cc-105">This document assumes that you are installing [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] for internal testing or demonstration purposes only.</span></span> <span data-ttu-id="7c3cc-106">它不规定任何最低安全帐户或设置。</span><span class="sxs-lookup"><span data-stu-id="7c3cc-106">It does not prescribe any minimum-security account or set up.</span></span> <span data-ttu-id="7c3cc-107">必须使用具有本主题中的所有过程的本地管理权限的帐户。</span><span class="sxs-lookup"><span data-stu-id="7c3cc-107">You must use an account that has local administrative permissions throughout the procedures in this topic.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="7c3cc-108">此示例不支持消息附件。</span><span class="sxs-lookup"><span data-stu-id="7c3cc-108">This sample does not support message attachments.</span></span>  
  
## <a name="filetransport-binding-files"></a><span data-ttu-id="7c3cc-109">FileTransport 绑定文件</span><span class="sxs-lookup"><span data-stu-id="7c3cc-109">FileTransport Binding Files</span></span>  
 <span data-ttu-id="7c3cc-110">FileTransport 示例包含两个绑定文件。</span><span class="sxs-lookup"><span data-stu-id="7c3cc-110">The FileTransport sample includes two binding files.</span></span> <span data-ttu-id="7c3cc-111">可以使用每个绑定文件来设置用于 BTARN 业务流程文件端口。</span><span class="sxs-lookup"><span data-stu-id="7c3cc-111">You can use each of these binding files to set up File ports for use with a BTARN orchestration.</span></span> <span data-ttu-id="7c3cc-112">这些绑定文件位于*\<驱动器\>*: \Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet \SDK\FileTransport。</span><span class="sxs-lookup"><span data-stu-id="7c3cc-112">These binding files are located in *\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet \SDK\FileTransport.</span></span> <span data-ttu-id="7c3cc-113">若要查看该业务流程的设置、 发送端口、 接收端口和接收位置，如记事本编辑器中打开每个绑定文件，如下所示。</span><span class="sxs-lookup"><span data-stu-id="7c3cc-113">Open each binding file in an editor like Notepad to see the settings for the orchestration, send port, receive port, and receive location, as listed below.</span></span>  
  
- <span data-ttu-id="7c3cc-114">PrivateInitiatorusingFileDrops.xml</span><span class="sxs-lookup"><span data-stu-id="7c3cc-114">PrivateInitiatorusingFileDrops.xml</span></span>  
  
  -   <span data-ttu-id="7c3cc-115">业务流程：Microsoft.Solutions.BTARN.PrivateInitiator.PrivateInitiatorProcess</span><span class="sxs-lookup"><span data-stu-id="7c3cc-115">Orchestration: Microsoft.Solutions.BTARN.PrivateInitiator.PrivateInitiatorProcess</span></span>  
  
  -   <span data-ttu-id="7c3cc-116">发送端口：PrivateInitiator_To_File</span><span class="sxs-lookup"><span data-stu-id="7c3cc-116">Send port: PrivateInitiator_To_File</span></span>  
  
  -   <span data-ttu-id="7c3cc-117">接收端口：File_To_PrivateInitiator</span><span class="sxs-lookup"><span data-stu-id="7c3cc-117">Receive port: File_To_PrivateInitiator</span></span>  
  
  -   <span data-ttu-id="7c3cc-118">接收位置：File_To_PrivateInitiator</span><span class="sxs-lookup"><span data-stu-id="7c3cc-118">Receive location: File_To_PrivateInitiator</span></span>  
  
- <span data-ttu-id="7c3cc-119">PrivateResponderusingFileDrops.xml</span><span class="sxs-lookup"><span data-stu-id="7c3cc-119">PrivateResponderusingFileDrops.xml</span></span>  
  
  -   <span data-ttu-id="7c3cc-120">业务流程：Microsoft.Solutions.BTARN.PrivateResponder.PrivateResponderProcess</span><span class="sxs-lookup"><span data-stu-id="7c3cc-120">Orchestration: Microsoft.Solutions.BTARN.PrivateResponder.PrivateResponderProcess</span></span>  
  
  -   <span data-ttu-id="7c3cc-121">发送端口：PrivateResponder_To_File</span><span class="sxs-lookup"><span data-stu-id="7c3cc-121">Send port: PrivateResponder_To_File</span></span>  
  
  -   <span data-ttu-id="7c3cc-122">接收端口：File_To_PrivateResponder</span><span class="sxs-lookup"><span data-stu-id="7c3cc-122">Receive port: File_To_PrivateResponder</span></span>  
  
  -   <span data-ttu-id="7c3cc-123">接收位置：File_To_PrivateResponder</span><span class="sxs-lookup"><span data-stu-id="7c3cc-123">Receive location: File_To_PrivateResponder</span></span>  
  
  <span data-ttu-id="7c3cc-124">以下过程介绍如何从绑定文件使用 BTSTask 命令导入绑定。</span><span class="sxs-lookup"><span data-stu-id="7c3cc-124">The following procedure describes how to import the bindings from the binding files using the BTSTask command.</span></span> <span data-ttu-id="7c3cc-125">有关详细信息，请参阅 BizTalk Server 帮助中的"ImportBindings 命令"主题。</span><span class="sxs-lookup"><span data-stu-id="7c3cc-125">For more information, see the "ImportBindings Command" topic in BizTalk Server Help.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="7c3cc-126">过程</span><span class="sxs-lookup"><span data-stu-id="7c3cc-126">Procedure</span></span>  
  
#### <a name="to-set-up-btarn-by-using-file-drop-folders"></a><span data-ttu-id="7c3cc-127">若要使用文件的放置文件夹设置 BTARN</span><span class="sxs-lookup"><span data-stu-id="7c3cc-127">To set up BTARN by using file drop folders</span></span>  
  
1.  <span data-ttu-id="7c3cc-128">打开 BizTalk 浏览器。</span><span class="sxs-lookup"><span data-stu-id="7c3cc-128">Open BizTalk Explorer.</span></span>  
  
2.  <span data-ttu-id="7c3cc-129">停止两个 LOB SQL 发送端口： PrivateInitiator_To_LOB 和 PrivateResponder_To_LOB。</span><span class="sxs-lookup"><span data-stu-id="7c3cc-129">Stop the two LOB SQL send ports, PrivateInitiator_To_LOB and PrivateResponder_To_LOB.</span></span>  
  
3.  <span data-ttu-id="7c3cc-130">禁用两个 Lob SQL 接收端口，LOB_To_PrivateInitiator 和 LOB_To_PrivateResponder。</span><span class="sxs-lookup"><span data-stu-id="7c3cc-130">Disable the two Lob SQL Receive ports, LOB_To_PrivateInitiator and LOB_To_PrivateResponder.</span></span>  
  
4.  <span data-ttu-id="7c3cc-131">取消登记 Microsoft.Solutions.BTARN.PrivateResponder.PrivateResponderProcess。</span><span class="sxs-lookup"><span data-stu-id="7c3cc-131">Unenlist Microsoft.Solutions.BTARN.PrivateResponder.PrivateResponderProcess.</span></span>  
  
5.  <span data-ttu-id="7c3cc-132">取消登记 Microsoft.Solutions.BTARN.PrivateInitiator.PrivateInitiatatorProcess。</span><span class="sxs-lookup"><span data-stu-id="7c3cc-132">Unenlist Microsoft.Solutions.BTARN.PrivateInitiator.PrivateInitiatatorProcess.</span></span>  
  
6.  <span data-ttu-id="7c3cc-133">创建 \FileDrops 文件夹 C:\Program Files\Microsoft BizTalk 的 BTARN 文件夹下\<版本\>Accelerator for RosettaNet，然后创建在 \FileDrops 下的以下文件夹结构：</span><span class="sxs-lookup"><span data-stu-id="7c3cc-133">Create a \FileDrops folder under the BTARN folder of C:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet , and then create the following folder structure under \FileDrops:</span></span>  
  
    -   <span data-ttu-id="7c3cc-134">\PrivateInitiator</span><span class="sxs-lookup"><span data-stu-id="7c3cc-134">\PrivateInitiator</span></span>  
  
         <span data-ttu-id="7c3cc-135">\FromLOB</span><span class="sxs-lookup"><span data-stu-id="7c3cc-135">\FromLOB</span></span>  
  
         <span data-ttu-id="7c3cc-136">\ToLOB</span><span class="sxs-lookup"><span data-stu-id="7c3cc-136">\ToLOB</span></span>  
  
    -   <span data-ttu-id="7c3cc-137">\PrivateResponder</span><span class="sxs-lookup"><span data-stu-id="7c3cc-137">\PrivateResponder</span></span>  
  
         <span data-ttu-id="7c3cc-138">\FromLOB</span><span class="sxs-lookup"><span data-stu-id="7c3cc-138">\FromLOB</span></span>  
  
         <span data-ttu-id="7c3cc-139">\ToLOB</span><span class="sxs-lookup"><span data-stu-id="7c3cc-139">\ToLOB</span></span>  
  
7.  <span data-ttu-id="7c3cc-140">运行以下命令 （假定 BTARN 安装在 c： 驱动器上）：</span><span class="sxs-lookup"><span data-stu-id="7c3cc-140">Run the following command (assuming that BTARN is installed on the C: drive):</span></span>  
  
    ```  
    BTSTask ImportBindings /Source:C:\Program Files\Microsoft BizTalk <version> Accelerator for RosettaNet\SDK\FileTransport\PrivateInitiatorusingFileDrops.xml  
    ```  
  
8.  <span data-ttu-id="7c3cc-141">运行以下命令 （假定 BTARN 安装在 c： 驱动器上）：</span><span class="sxs-lookup"><span data-stu-id="7c3cc-141">Run the following command (assuming that BTARN is installed on the C: drive):</span></span>  
  
    ```  
    BTSTask ImportBindings /Source:C:\Program Files\Microsoft BizTalk <version> Accelerator for RosettaNet\SDK\FileTransport\PrivateResponderusingFileDrops.xml  
    ```  
  
9. <span data-ttu-id="7c3cc-142">启动发送端口：PrivateInitiator_To_File 和 PrivateResponder_To_File。</span><span class="sxs-lookup"><span data-stu-id="7c3cc-142">Start the send ports: PrivateInitiator_To_File and PrivateResponder_To_File.</span></span>  
  
10. <span data-ttu-id="7c3cc-143">启用接收端口：LOB_To_PrivateInitiator 和 LOB_To_PrivateResponder。</span><span class="sxs-lookup"><span data-stu-id="7c3cc-143">Enable the receive ports: LOB_To_PrivateInitiator and LOB_To_PrivateResponder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c3cc-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="7c3cc-144">See Also</span></span>  
 [<span data-ttu-id="7c3cc-145">消息传送示例</span><span class="sxs-lookup"><span data-stu-id="7c3cc-145">Messaging Samples</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/messaging-samples.md)