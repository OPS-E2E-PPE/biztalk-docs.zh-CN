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
ms.openlocfilehash: 682e87e2cfca4906b0f9c582d5e33a235525e293
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329106"
---
# <a name="known-issues-with-the-ftp-adapter"></a><span data-ttu-id="30d71-102">FTP 适配器的已知的问题</span><span class="sxs-lookup"><span data-stu-id="30d71-102">Known Issues with the FTP Adapter</span></span>
<span data-ttu-id="30d71-103">本部分包含可能帮助您避免错误的信息。</span><span class="sxs-lookup"><span data-stu-id="30d71-103">This section contains information that may help you avoid errors.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="30d71-104">已知问题</span><span class="sxs-lookup"><span data-stu-id="30d71-104">Known Issues</span></span>  
  
#### <a name="data-may-be-duplicated-or-lost-when-you-receive-data-in-biztalk-server-by-using-the-ftp-adapter"></a><span data-ttu-id="30d71-105">数据可能会重复或丢失时通过使用 FTP 适配器，BizTalk Server 中接收数据</span><span class="sxs-lookup"><span data-stu-id="30d71-105">Data may be duplicated or lost when you receive data in BizTalk Server by using the FTP adapter</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="30d71-106">问题</span><span class="sxs-lookup"><span data-stu-id="30d71-106">Problem</span></span>  
 <span data-ttu-id="30d71-107">数据会重复或丢失时接收中的数据[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过使用 FTP 适配器。</span><span class="sxs-lookup"><span data-stu-id="30d71-107">Data is duplicated or lost when you receive data in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] by using the FTP Adapter.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="30d71-108">原因</span><span class="sxs-lookup"><span data-stu-id="30d71-108">Cause</span></span>  
 <span data-ttu-id="30d71-109">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] FTP 适配器使用 FTP 客户端协议轮询指定的 FTP 服务器，并从"按原样。"的服务器中检索数据</span><span class="sxs-lookup"><span data-stu-id="30d71-109">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] FTP adapter uses the FTP client protocol to poll the designated FTP server and retrieves data from the server "as is."</span></span> <span data-ttu-id="30d71-110">FTP 适配器不会验证它检索任何数据。</span><span class="sxs-lookup"><span data-stu-id="30d71-110">The FTP adapter does not validate any data that it retrieves.</span></span> <span data-ttu-id="30d71-111">FTP 适配器将检索到的文档发送到 BizTalk 消息引擎进行处理，然后从 FTP 服务器中删除原始文档。</span><span class="sxs-lookup"><span data-stu-id="30d71-111">The FTP adapter sends the retrieved document to the BizTalk Messaging Engine for processing and then it deletes the original document from the FTP server.</span></span> <span data-ttu-id="30d71-112">如果 FTP 适配器从 FTP 服务器仍被写入到主机应用程序检索文档，检索到的文档将不完整。</span><span class="sxs-lookup"><span data-stu-id="30d71-112">If the FTP adapter retrieves a document from the FTP server that is still being written to by the host application, the retrieved document will be incomplete.</span></span> <span data-ttu-id="30d71-113">如果 FTP 适配器检索不完整的原始文档的副本，重复数据或数据丢失可能出现在以下方案中：</span><span class="sxs-lookup"><span data-stu-id="30d71-113">If the FTP adapter retrieves an incomplete copy of the original document, data duplication or data loss may occur in the following scenarios:</span></span>  
  
-   <span data-ttu-id="30d71-114">如果原始文档仍正在由主机应用程序写入 FTP 服务器，FTP 适配器不能删除该文档，并将在下一个轮询间隔配置为接收位置检索文档的另一个副本。</span><span class="sxs-lookup"><span data-stu-id="30d71-114">If the original document is still being written to the FTP server by the host application, the FTP adapter cannot delete the document and will retrieve another copy of the document at the next polling interval that is configured for the receive location.</span></span> <span data-ttu-id="30d71-115">此行为会导致出现文档重复。</span><span class="sxs-lookup"><span data-stu-id="30d71-115">This behavior causes document duplication to occur.</span></span>  
  
-   <span data-ttu-id="30d71-116">如果主机应用程序已完成将文档写入 FTP 服务器，将删除文档。</span><span class="sxs-lookup"><span data-stu-id="30d71-116">If the host application has finished writing the document to the FTP server, the document will be deleted.</span></span> <span data-ttu-id="30d71-117">此行为将导致出现数据丢失。</span><span class="sxs-lookup"><span data-stu-id="30d71-117">This behavior will cause data loss to occur.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="30d71-118">解决方法</span><span class="sxs-lookup"><span data-stu-id="30d71-118">Resolution</span></span>  
 <span data-ttu-id="30d71-119">若要解决此问题，请使用以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="30d71-119">To work around this behavior, use one of the following methods:</span></span>  
  
- <span data-ttu-id="30d71-120">配置主机应用程序要写入到临时文件夹与公共 FTP 文件夹位于同一硬盘上，并定期将临时文件夹的内容移动到 FTP 文件夹。</span><span class="sxs-lookup"><span data-stu-id="30d71-120">Configure the host application to write to a temporary folder on the same hard disk as the public FTP folder and to periodically move the contents of the temporary folder to the FTP folder.</span></span> <span data-ttu-id="30d71-121">临时文件夹应与公共 FTP 文件夹，以确保移动操作为原子同一硬盘上。</span><span class="sxs-lookup"><span data-stu-id="30d71-121">The temporary folder should be on the same hard disk as the public FTP folder to make sure that the move operation is atomic.</span></span> <span data-ttu-id="30d71-122">以原子操作是功能上无法分割的操作。</span><span class="sxs-lookup"><span data-stu-id="30d71-122">An atomic operation is an operation that is functionally indivisible.</span></span> <span data-ttu-id="30d71-123">如果您数据写入公共 FTP 文件夹使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]FTP 适配器，您可以执行此操作通过在 FTP 传输属性对话框中指定临时文件夹属性时，发送端口配置。</span><span class="sxs-lookup"><span data-stu-id="30d71-123">If you write data to the public FTP folder by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] FTP adapter, you can do this by specifying a Temporary Folder property in the FTP Transport Properties dialog box when you configure a send port.</span></span> <span data-ttu-id="30d71-124">如果您指定的临时文件夹属性，请确保此文件夹与公共 FTP 文件夹位于同一个物理磁盘上。</span><span class="sxs-lookup"><span data-stu-id="30d71-124">If you specify a Temporary Folder property, make sure that this folder is on the same physical disk as the public FTP folder.</span></span>  
  
- <span data-ttu-id="30d71-125">配置 FTP 接收位置主机应用程序不向 FTP 服务器写入数据时运行的服务时段。</span><span class="sxs-lookup"><span data-stu-id="30d71-125">Configure the FTP receive location to operate within a service window when the host application is not writing data to the FTP server.</span></span> <span data-ttu-id="30d71-126">在配置的接收位置属性时，可以指定服务时段。</span><span class="sxs-lookup"><span data-stu-id="30d71-126">You can specify the service window when you configure the receive location properties.</span></span>  
  
#### <a name="ftp-adapter-does-not-support-revocation-checks-on-the-server-certificates"></a><span data-ttu-id="30d71-127">FTP 适配器不支持对服务器证书的吊销检查</span><span class="sxs-lookup"><span data-stu-id="30d71-127">FTP Adapter does not support revocation checks on the server certificates</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="30d71-128">问题</span><span class="sxs-lookup"><span data-stu-id="30d71-128">Problem</span></span>  
 <span data-ttu-id="30d71-129">FTP 适配器在 BizTalk Server 中的得到了增强，可支持安全文件传输到和从 FTPS 服务器使用 SSL/TLS。</span><span class="sxs-lookup"><span data-stu-id="30d71-129">The FTP adapter in BizTalk Server is enhanced to support secure file transfer to and from an FTPS server using SSL/TLS.</span></span> <span data-ttu-id="30d71-130">证书吊销列表 (CRL) 包含一系列已被吊销，并且将不再有效的证书。</span><span class="sxs-lookup"><span data-stu-id="30d71-130">The Certificate Revocation List (CRL) contains a list of certificates that have been revoked and are no longer valid.</span></span> <span data-ttu-id="30d71-131">FTP 适配器不能查阅 CRL 进行身份验证服务器证书。</span><span class="sxs-lookup"><span data-stu-id="30d71-131">The FTP adapter does not consult the CRL for authenticating the server certificate.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="30d71-132">原因</span><span class="sxs-lookup"><span data-stu-id="30d71-132">Cause</span></span>  
 <span data-ttu-id="30d71-133">根据设计，FTP 适配器不能查阅 CRL 再接受服务器证书。</span><span class="sxs-lookup"><span data-stu-id="30d71-133">By design, the FTP adapter does not consult the CRL before accepting a server certificate.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="30d71-134">解决方法</span><span class="sxs-lookup"><span data-stu-id="30d71-134">Resolution</span></span>  
 <span data-ttu-id="30d71-135">必需的; 不不执行任何操作此行为是默认设置。</span><span class="sxs-lookup"><span data-stu-id="30d71-135">No action is required; this behavior is by design.</span></span>  
  
#### <a name="ftp-adapter-downloads-files-larger-than-max-file-size"></a><span data-ttu-id="30d71-136">FTP 适配器下载大于最大文件大小的文件</span><span class="sxs-lookup"><span data-stu-id="30d71-136">FTP Adapter downloads files larger than Max File Size</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="30d71-137">问题</span><span class="sxs-lookup"><span data-stu-id="30d71-137">Problem</span></span>  
 <span data-ttu-id="30d71-138">FTP 接收适配器的下载文件的大小大于指定的最大文件大小属性，从以下的 FTP 服务器：</span><span class="sxs-lookup"><span data-stu-id="30d71-138">The FTP receive adapter downloads files whose size is larger than the specified Max File Size property from the following FTP servers:</span></span>  
  
-   <span data-ttu-id="30d71-139">AIX</span><span class="sxs-lookup"><span data-stu-id="30d71-139">AIX</span></span>  
  
-   <span data-ttu-id="30d71-140">MVS</span><span class="sxs-lookup"><span data-stu-id="30d71-140">MVS</span></span>  
  
-   <span data-ttu-id="30d71-141">AS400</span><span class="sxs-lookup"><span data-stu-id="30d71-141">AS400</span></span>  
  
-   <span data-ttu-id="30d71-142">GXS</span><span class="sxs-lookup"><span data-stu-id="30d71-142">GXS</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="30d71-143">原因</span><span class="sxs-lookup"><span data-stu-id="30d71-143">Cause</span></span>  
 <span data-ttu-id="30d71-144">按照设计，FTP 适配器不会接受的最大文件大小，如果从这些 FTP 服务器下载文件。</span><span class="sxs-lookup"><span data-stu-id="30d71-144">By design, the FTP adapter does not respect the maximum file size when downloading files from these FTP servers.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="30d71-145">解决方法</span><span class="sxs-lookup"><span data-stu-id="30d71-145">Resolution</span></span>  
 <span data-ttu-id="30d71-146">必需的; 不不执行任何操作此行为是默认设置。</span><span class="sxs-lookup"><span data-stu-id="30d71-146">No action is required; this behavior is by design.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30d71-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="30d71-147">See Also</span></span>  
 <span data-ttu-id="30d71-148">[如何配置 FTP 接收位置](http://msdn.microsoft.com/library/1d8fde35-f787-4a5e-a8bd-8c418d0f75c3) </span><span class="sxs-lookup"><span data-stu-id="30d71-148">[How to Configure an FTP Receive Location](http://msdn.microsoft.com/library/1d8fde35-f787-4a5e-a8bd-8c418d0f75c3) </span></span>  
 [<span data-ttu-id="30d71-149">FTP 适配器故障排除</span><span class="sxs-lookup"><span data-stu-id="30d71-149">Troubleshooting the FTP Adapter</span></span>](../core/troubleshooting-the-ftp-adapter.md)