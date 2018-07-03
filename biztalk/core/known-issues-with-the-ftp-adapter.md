---
title: 使用 FTP 适配器的已知问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9e58f2db-9ec5-41fe-af02-9a7d60a217db
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fcab9b35759d491c0732cfb2613a2fd4fe992a3e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022483"
---
# <a name="known-issues-with-the-ftp-adapter"></a><span data-ttu-id="14cb2-102">FTP 适配器的已知的问题</span><span class="sxs-lookup"><span data-stu-id="14cb2-102">Known Issues with the FTP Adapter</span></span>
<span data-ttu-id="14cb2-103">本部分包含可帮助你避免出现错误的信息。</span><span class="sxs-lookup"><span data-stu-id="14cb2-103">This section contains information that may help you avoid errors.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="14cb2-104">已知问题</span><span class="sxs-lookup"><span data-stu-id="14cb2-104">Known Issues</span></span>  
  
#### <a name="data-may-be-duplicated-or-lost-when-you-receive-data-in-biztalk-server-by-using-the-ftp-adapter"></a><span data-ttu-id="14cb2-105">数据可能会重复或丢失时通过使用 FTP 适配器，BizTalk Server 中接收数据</span><span class="sxs-lookup"><span data-stu-id="14cb2-105">Data may be duplicated or lost when you receive data in BizTalk Server by using the FTP adapter</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="14cb2-106">问题</span><span class="sxs-lookup"><span data-stu-id="14cb2-106">Problem</span></span>  
 <span data-ttu-id="14cb2-107">在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中使用 FTP 适配器接收数据时，数据会重复或丢失。</span><span class="sxs-lookup"><span data-stu-id="14cb2-107">Data is duplicated or lost when you receive data in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] by using the FTP Adapter.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="14cb2-108">原因</span><span class="sxs-lookup"><span data-stu-id="14cb2-108">Cause</span></span>  
 <span data-ttu-id="14cb2-109">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] FTP 适配器使用 FTP 客户端协议轮询指定的 FTP 服务器，并“按原样”从服务器检索数据。</span><span class="sxs-lookup"><span data-stu-id="14cb2-109">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] FTP adapter uses the FTP client protocol to poll the designated FTP server and retrieves data from the server "as is."</span></span> <span data-ttu-id="14cb2-110">FTP 适配器不会对所检索的任何数据执行验证。</span><span class="sxs-lookup"><span data-stu-id="14cb2-110">The FTP adapter does not validate any data that it retrieves.</span></span> <span data-ttu-id="14cb2-111">FTP 适配器只是将检索到的文档发送到 BizTalk 消息引擎以进行处理，然后从 FTP 服务器中删除原始文档。</span><span class="sxs-lookup"><span data-stu-id="14cb2-111">The FTP adapter sends the retrieved document to the BizTalk Messaging Engine for processing and then it deletes the original document from the FTP server.</span></span> <span data-ttu-id="14cb2-112">如果 FTP 适配器从 FTP 服务器检索的文档仍在由主机应用程序进行写入，则检索到的文档将不完整。</span><span class="sxs-lookup"><span data-stu-id="14cb2-112">If the FTP adapter retrieves a document from the FTP server that is still being written to by the host application, the retrieved document will be incomplete.</span></span> <span data-ttu-id="14cb2-113">如果 FTP 适配器检索到原始文档的不完整副本，则可能会发生数据重复或数据丢失的情况，如下所述：</span><span class="sxs-lookup"><span data-stu-id="14cb2-113">If the FTP adapter retrieves an incomplete copy of the original document, data duplication or data loss may occur in the following scenarios:</span></span>  
  
-   <span data-ttu-id="14cb2-114">如果原始文档仍在由主机应用程序写入 FTP 服务器，则 FTP 适配器将无法删除该文档，并将在为接收位置配置的下一轮询间隔期间检索到该文档的另一个副本。</span><span class="sxs-lookup"><span data-stu-id="14cb2-114">If the original document is still being written to the FTP server by the host application, the FTP adapter cannot delete the document and will retrieve another copy of the document at the next polling interval that is configured for the receive location.</span></span> <span data-ttu-id="14cb2-115">这一行为将导致出现文档重复。</span><span class="sxs-lookup"><span data-stu-id="14cb2-115">This behavior causes document duplication to occur.</span></span>  
  
-   <span data-ttu-id="14cb2-116">如果主机应用程序已完成将文档写入 FTP 服务器的过程，则该文档将被删除。</span><span class="sxs-lookup"><span data-stu-id="14cb2-116">If the host application has finished writing the document to the FTP server, the document will be deleted.</span></span> <span data-ttu-id="14cb2-117">这一行为将导致出现数据丢失。</span><span class="sxs-lookup"><span data-stu-id="14cb2-117">This behavior will cause data loss to occur.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="14cb2-118">解决方法</span><span class="sxs-lookup"><span data-stu-id="14cb2-118">Resolution</span></span>  
 <span data-ttu-id="14cb2-119">若要解决此问题，请使用以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="14cb2-119">To work around this behavior, use one of the following methods:</span></span>  
  
- <span data-ttu-id="14cb2-120">将主机应用程序配置成向公共 FTP 文件夹所在硬盘上的一个临时文件夹中进行写入，然后定期将临时文件夹的内容移动到 FTP 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="14cb2-120">Configure the host application to write to a temporary folder on the same hard disk as the public FTP folder and to periodically move the contents of the temporary folder to the FTP folder.</span></span> <span data-ttu-id="14cb2-121">临时文件夹应与公共 FTP 文件夹位于同一硬盘上，以确保移动操作为原子操作。</span><span class="sxs-lookup"><span data-stu-id="14cb2-121">The temporary folder should be on the same hard disk as the public FTP folder to make sure that the move operation is atomic.</span></span> <span data-ttu-id="14cb2-122">原子操作是功能上无法分割的操作。</span><span class="sxs-lookup"><span data-stu-id="14cb2-122">An atomic operation is an operation that is functionally indivisible.</span></span> <span data-ttu-id="14cb2-123">如果您通过使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] FTP 适配器将数据写入公共 FTP 文件夹，则配置发送端口时，可以通过在“FTP 传输属性”对话框中指定“临时文件夹”属性来实现。</span><span class="sxs-lookup"><span data-stu-id="14cb2-123">If you write data to the public FTP folder by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] FTP adapter, you can do this by specifying a Temporary Folder property in the FTP Transport Properties dialog box when you configure a send port.</span></span> <span data-ttu-id="14cb2-124">如果指定“临时文件夹”属性，请确保此文件夹与公共 FTP 文件夹位于同一物理磁盘上。</span><span class="sxs-lookup"><span data-stu-id="14cb2-124">If you specify a Temporary Folder property, make sure that this folder is on the same physical disk as the public FTP folder.</span></span>  
  
- <span data-ttu-id="14cb2-125">将 FTP 接收位置配置为在主机应用程序不向 FTP 服务器写入数据的服务时段执行操作。</span><span class="sxs-lookup"><span data-stu-id="14cb2-125">Configure the FTP receive location to operate within a service window when the host application is not writing data to the FTP server.</span></span> <span data-ttu-id="14cb2-126">可以在配置接收位置属性时指定该服务时段。</span><span class="sxs-lookup"><span data-stu-id="14cb2-126">You can specify the service window when you configure the receive location properties.</span></span>  
  
#### <a name="ftp-adapter-does-not-support-revocation-checks-on-the-server-certificates"></a><span data-ttu-id="14cb2-127">FTP 适配器不支持对服务器证书执行吊销检查。</span><span class="sxs-lookup"><span data-stu-id="14cb2-127">FTP Adapter does not support revocation checks on the server certificates</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="14cb2-128">问题</span><span class="sxs-lookup"><span data-stu-id="14cb2-128">Problem</span></span>  
 <span data-ttu-id="14cb2-129">FTP 适配器在 BizTalk Server 中的得到了增强，可支持安全文件传输到和从 FTPS 服务器使用 SSL/TLS。</span><span class="sxs-lookup"><span data-stu-id="14cb2-129">The FTP adapter in BizTalk Server is enhanced to support secure file transfer to and from an FTPS server using SSL/TLS.</span></span> <span data-ttu-id="14cb2-130">证书吊销列表 (CRL) 包含已吊销的及不再有效的证书列表。</span><span class="sxs-lookup"><span data-stu-id="14cb2-130">The Certificate Revocation List (CRL) contains a list of certificates that have been revoked and are no longer valid.</span></span> <span data-ttu-id="14cb2-131">FTP 适配器不能查阅 CRL 来对服务器证书进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="14cb2-131">The FTP adapter does not consult the CRL for authenticating the server certificate.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="14cb2-132">原因</span><span class="sxs-lookup"><span data-stu-id="14cb2-132">Cause</span></span>  
 <span data-ttu-id="14cb2-133">根据设计，FTP 适配器不能查阅 CRL 再接受服务器证书。</span><span class="sxs-lookup"><span data-stu-id="14cb2-133">By design, the FTP adapter does not consult the CRL before accepting a server certificate.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="14cb2-134">解决方法</span><span class="sxs-lookup"><span data-stu-id="14cb2-134">Resolution</span></span>  
 <span data-ttu-id="14cb2-135">必需的; 不不执行任何操作此行为是默认设置。</span><span class="sxs-lookup"><span data-stu-id="14cb2-135">No action is required; this behavior is by design.</span></span>  
  
#### <a name="ftp-adapter-downloads-files-larger-than-max-file-size"></a><span data-ttu-id="14cb2-136">FTP 适配器下载大于最大文件大小的文件</span><span class="sxs-lookup"><span data-stu-id="14cb2-136">FTP Adapter downloads files larger than Max File Size</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="14cb2-137">问题</span><span class="sxs-lookup"><span data-stu-id="14cb2-137">Problem</span></span>  
 <span data-ttu-id="14cb2-138">FTP 接收适配器的下载文件的大小大于指定的最大文件大小属性，从以下的 FTP 服务器：</span><span class="sxs-lookup"><span data-stu-id="14cb2-138">The FTP receive adapter downloads files whose size is larger than the specified Max File Size property from the following FTP servers:</span></span>  
  
-   <span data-ttu-id="14cb2-139">AIX</span><span class="sxs-lookup"><span data-stu-id="14cb2-139">AIX</span></span>  
  
-   <span data-ttu-id="14cb2-140">MVS</span><span class="sxs-lookup"><span data-stu-id="14cb2-140">MVS</span></span>  
  
-   <span data-ttu-id="14cb2-141">AS400</span><span class="sxs-lookup"><span data-stu-id="14cb2-141">AS400</span></span>  
  
-   <span data-ttu-id="14cb2-142">GXS</span><span class="sxs-lookup"><span data-stu-id="14cb2-142">GXS</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="14cb2-143">原因</span><span class="sxs-lookup"><span data-stu-id="14cb2-143">Cause</span></span>  
 <span data-ttu-id="14cb2-144">按照设计，FTP 适配器不会接受的最大文件大小，如果从这些 FTP 服务器下载文件。</span><span class="sxs-lookup"><span data-stu-id="14cb2-144">By design, the FTP adapter does not respect the maximum file size when downloading files from these FTP servers.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="14cb2-145">解决方法</span><span class="sxs-lookup"><span data-stu-id="14cb2-145">Resolution</span></span>  
 <span data-ttu-id="14cb2-146">必需的; 不不执行任何操作此行为是默认设置。</span><span class="sxs-lookup"><span data-stu-id="14cb2-146">No action is required; this behavior is by design.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14cb2-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="14cb2-147">See Also</span></span>  
 <span data-ttu-id="14cb2-148">[如何配置 FTP 接收位置](http://msdn.microsoft.com/library/1d8fde35-f787-4a5e-a8bd-8c418d0f75c3) </span><span class="sxs-lookup"><span data-stu-id="14cb2-148">[How to Configure an FTP Receive Location](http://msdn.microsoft.com/library/1d8fde35-f787-4a5e-a8bd-8c418d0f75c3) </span></span>  
 [<span data-ttu-id="14cb2-149">FTP 适配器故障排除</span><span class="sxs-lookup"><span data-stu-id="14cb2-149">Troubleshooting the FTP Adapter</span></span>](../core/troubleshooting-the-ftp-adapter.md)