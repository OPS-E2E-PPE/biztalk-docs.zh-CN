---
title: "FileTransport 示例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a32c8cbf-0c17-4237-b2a3-9d21faa13496
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 495e4cfe4c9c9b9d7ae16ee58f7831ad5447d37b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="filetransport-sample"></a><span data-ttu-id="402eb-102">FileTransport 示例</span><span class="sxs-lookup"><span data-stu-id="402eb-102">FileTransport Sample</span></span>
<span data-ttu-id="402eb-103">FileTransport 示例演示如何配置[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]用于文件端口，而不是 SQL 端口。</span><span class="sxs-lookup"><span data-stu-id="402eb-103">The FileTransport sample demonstrates how to configure [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] to use File ports, instead of SQL ports.</span></span> <span data-ttu-id="402eb-104">FileTransport 示例使用文件传输协议 (FTP) 发送和接收消息，而不是使用 HTTP。</span><span class="sxs-lookup"><span data-stu-id="402eb-104">The FileTransport sample uses File Transport Protocol (FTP) to send and receive messages, instead of HTTP.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="402eb-105">此文档假设你安装 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 只是为了进行内部测试或进行演示。</span><span class="sxs-lookup"><span data-stu-id="402eb-105">This document assumes that you are installing [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] for internal testing or demonstration purposes only.</span></span> <span data-ttu-id="402eb-106">文档中没有涉及任何最低安全帐户或设置。</span><span class="sxs-lookup"><span data-stu-id="402eb-106">It does not prescribe any minimum-security account or set up.</span></span> <span data-ttu-id="402eb-107">在执行本主题的所有过程时，都必须使用具有本地管理权限的帐户。</span><span class="sxs-lookup"><span data-stu-id="402eb-107">You must use an account that has local administrative permissions throughout the procedures in this topic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="402eb-108">此示例不支持消息附件。</span><span class="sxs-lookup"><span data-stu-id="402eb-108">This sample does not support message attachments.</span></span>  
  
## <a name="filetransport-binding-files"></a><span data-ttu-id="402eb-109">FileTransport 绑定文件</span><span class="sxs-lookup"><span data-stu-id="402eb-109">FileTransport Binding Files</span></span>  
 <span data-ttu-id="402eb-110">FileTransport 示例包含两个绑定文件。</span><span class="sxs-lookup"><span data-stu-id="402eb-110">The FileTransport sample includes two binding files.</span></span> <span data-ttu-id="402eb-111">你可以使用这些绑定文件中的任何一个来设置用于 BTARN 业务流程的文件端口。</span><span class="sxs-lookup"><span data-stu-id="402eb-111">You can use each of these binding files to set up File ports for use with a BTARN orchestration.</span></span> <span data-ttu-id="402eb-112">这些绑定文件位于*\<驱动器 >*: files\microsoft BizTalk\<版本 > RosettaNet \SDK\FileTransport 快捷键。</span><span class="sxs-lookup"><span data-stu-id="402eb-112">These binding files are located in *\<drive>*:\Program Files\Microsoft BizTalk \<version> Accelerator for RosettaNet \SDK\FileTransport.</span></span> <span data-ttu-id="402eb-113">在编辑器（如记事本）中打开每个绑定文件，可查看业务流程、发送端口、接收端口和接收位置的设置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="402eb-113">Open each binding file in an editor like Notepad to see the settings for the orchestration, send port, receive port, and receive location, as listed below.</span></span>  
  
-   <span data-ttu-id="402eb-114">PrivateInitiatorusingFileDrops.xml</span><span class="sxs-lookup"><span data-stu-id="402eb-114">PrivateInitiatorusingFileDrops.xml</span></span>  
  
    -   <span data-ttu-id="402eb-115">业务流程：Microsoft.Solutions.BTARN.PrivateInitiator.PrivateInitiatorProcess</span><span class="sxs-lookup"><span data-stu-id="402eb-115">Orchestration: Microsoft.Solutions.BTARN.PrivateInitiator.PrivateInitiatorProcess</span></span>  
  
    -   <span data-ttu-id="402eb-116">发送端口：PrivateInitiator_To_File</span><span class="sxs-lookup"><span data-stu-id="402eb-116">Send port: PrivateInitiator_To_File</span></span>  
  
    -   <span data-ttu-id="402eb-117">接收端口：File_To_PrivateInitiator</span><span class="sxs-lookup"><span data-stu-id="402eb-117">Receive port: File_To_PrivateInitiator</span></span>  
  
    -   <span data-ttu-id="402eb-118">接收位置：File_To_PrivateInitiator</span><span class="sxs-lookup"><span data-stu-id="402eb-118">Receive location: File_To_PrivateInitiator</span></span>  
  
-   <span data-ttu-id="402eb-119">PrivateResponderusingFileDrops.xml</span><span class="sxs-lookup"><span data-stu-id="402eb-119">PrivateResponderusingFileDrops.xml</span></span>  
  
    -   <span data-ttu-id="402eb-120">业务流程：Microsoft.Solutions.BTARN.PrivateResponder.PrivateResponderProcess</span><span class="sxs-lookup"><span data-stu-id="402eb-120">Orchestration: Microsoft.Solutions.BTARN.PrivateResponder.PrivateResponderProcess</span></span>  
  
    -   <span data-ttu-id="402eb-121">发送端口：PrivateResponder_To_File</span><span class="sxs-lookup"><span data-stu-id="402eb-121">Send port: PrivateResponder_To_File</span></span>  
  
    -   <span data-ttu-id="402eb-122">接收端口：File_To_PrivateResponder</span><span class="sxs-lookup"><span data-stu-id="402eb-122">Receive port: File_To_PrivateResponder</span></span>  
  
    -   <span data-ttu-id="402eb-123">接收位置：File_To_PrivateResponder</span><span class="sxs-lookup"><span data-stu-id="402eb-123">Receive location: File_To_PrivateResponder</span></span>  
  
 <span data-ttu-id="402eb-124">以下过程介绍如何使用 BTSTask 命令从绑定文件导入绑定。</span><span class="sxs-lookup"><span data-stu-id="402eb-124">The following procedure describes how to import the bindings from the binding files using the BTSTask command.</span></span> <span data-ttu-id="402eb-125">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] 帮助中的“ImportBindings 命令”主题。</span><span class="sxs-lookup"><span data-stu-id="402eb-125">For more information, see the "ImportBindings Command" topic in [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] Help.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="402eb-126">过程</span><span class="sxs-lookup"><span data-stu-id="402eb-126">Procedure</span></span>  
  
#### <a name="to-set-up-btarn-by-using-file-drop-folders"></a><span data-ttu-id="402eb-127">使用“文件存放”文件夹来设置 BTARN</span><span class="sxs-lookup"><span data-stu-id="402eb-127">To set up BTARN by using file drop folders</span></span>  
  
1.  <span data-ttu-id="402eb-128">打开 BizTalk 浏览器。</span><span class="sxs-lookup"><span data-stu-id="402eb-128">Open BizTalk Explorer.</span></span>  
  
2.  <span data-ttu-id="402eb-129">停止两个 LOB SQL 发送端口：PrivateInitiator_To_LOB 和 PrivateResponder_To_LOB。</span><span class="sxs-lookup"><span data-stu-id="402eb-129">Stop the two LOB SQL send ports, PrivateInitiator_To_LOB and PrivateResponder_To_LOB.</span></span>  
  
3.  <span data-ttu-id="402eb-130">禁用两个 Lob SQL 接收端口：LOB_To_PrivateInitiator 和 LOB_To_PrivateResponder。</span><span class="sxs-lookup"><span data-stu-id="402eb-130">Disable the two Lob SQL Receive ports, LOB_To_PrivateInitiator and LOB_To_PrivateResponder.</span></span>  
  
4.  <span data-ttu-id="402eb-131">取消登记 Microsoft.Solutions.BTARN.PrivateResponder.PrivateResponderProcess。</span><span class="sxs-lookup"><span data-stu-id="402eb-131">Unenlist Microsoft.Solutions.BTARN.PrivateResponder.PrivateResponderProcess.</span></span>  
  
5.  <span data-ttu-id="402eb-132">取消登记 Microsoft.Solutions.BTARN.PrivateInitiator.PrivateInitiatatorProcess。</span><span class="sxs-lookup"><span data-stu-id="402eb-132">Unenlist Microsoft.Solutions.BTARN.PrivateInitiator.PrivateInitiatatorProcess.</span></span>  
  
6.  <span data-ttu-id="402eb-133">创建 \FileDrops 文件夹 C:\Program Files\Microsoft BizTalk BTARN 文件夹下的\<版本 > Accelerator for RosettaNet，然后创建 \FileDrops 下的以下文件夹结构：</span><span class="sxs-lookup"><span data-stu-id="402eb-133">Create a \FileDrops folder under the BTARN folder of C:\Program Files\Microsoft BizTalk \<version> Accelerator for RosettaNet , and then create the following folder structure under \FileDrops:</span></span>  
  
    -   <span data-ttu-id="402eb-134">\PrivateInitiator</span><span class="sxs-lookup"><span data-stu-id="402eb-134">\PrivateInitiator</span></span>  
  
         <span data-ttu-id="402eb-135">\FromLOB</span><span class="sxs-lookup"><span data-stu-id="402eb-135">\FromLOB</span></span>  
  
         <span data-ttu-id="402eb-136">\ToLOB</span><span class="sxs-lookup"><span data-stu-id="402eb-136">\ToLOB</span></span>  
  
    -   <span data-ttu-id="402eb-137">\PrivateResponder</span><span class="sxs-lookup"><span data-stu-id="402eb-137">\PrivateResponder</span></span>  
  
         <span data-ttu-id="402eb-138">\FromLOB</span><span class="sxs-lookup"><span data-stu-id="402eb-138">\FromLOB</span></span>  
  
         <span data-ttu-id="402eb-139">\ToLOB</span><span class="sxs-lookup"><span data-stu-id="402eb-139">\ToLOB</span></span>  
  
7.  <span data-ttu-id="402eb-140">运行以下命令（假定 BTARN 安装在 C: 驱动器上）：</span><span class="sxs-lookup"><span data-stu-id="402eb-140">Run the following command (assuming that BTARN is installed on the C: drive):</span></span>  
  
    ```  
    BTSTask ImportBindings /Source:C:\Program Files\Microsoft BizTalk <version> Accelerator for RosettaNet\SDK\FileTransport\PrivateInitiatorusingFileDrops.xml  
    ```  
  
8.  <span data-ttu-id="402eb-141">运行以下命令（假定 BTARN 安装在 C: 驱动器上）：</span><span class="sxs-lookup"><span data-stu-id="402eb-141">Run the following command (assuming that BTARN is installed on the C: drive):</span></span>  
  
    ```  
    BTSTask ImportBindings /Source:C:\Program Files\Microsoft BizTalk <version> Accelerator for RosettaNet\SDK\FileTransport\PrivateResponderusingFileDrops.xml  
    ```  
  
9. <span data-ttu-id="402eb-142">启动发送端口：PrivateInitiator_To_File 和 PrivateResponder_To_File。</span><span class="sxs-lookup"><span data-stu-id="402eb-142">Start the send ports: PrivateInitiator_To_File and PrivateResponder_To_File.</span></span>  
  
10. <span data-ttu-id="402eb-143">启用接收端口：LOB_To_PrivateInitiator 和 LOB_To_PrivateResponder。</span><span class="sxs-lookup"><span data-stu-id="402eb-143">Enable the receive ports: LOB_To_PrivateInitiator and LOB_To_PrivateResponder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="402eb-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="402eb-144">See Also</span></span>  
 [<span data-ttu-id="402eb-145">消息传送示例</span><span class="sxs-lookup"><span data-stu-id="402eb-145">Messaging Samples</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/messaging-samples.md)