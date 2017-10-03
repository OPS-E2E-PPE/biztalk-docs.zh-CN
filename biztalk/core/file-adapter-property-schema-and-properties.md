---
title: "文件适配器属性架构和属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring [File adapters], properties
- schemas, File adapters
- File adapters, schemas
- Password property [File adapters]
- ReceivedFileName property [File adapters]
- configuring [File adapters], schemas
- CopyMode property [File adapters]
- AllowCacheOnWrite property [File adapters]
- FileCreationTime property [File adapters]
- UserName property, File adapters
- File adapters, properties
- UserName property
ms.assetid: c5ae5339-67bf-4fde-a721-5b1aa3b9caca
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37e1c6860b002b41555337a0bf7e8cb931f2c2bf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="file-adapter-property-schema-and-properties"></a><span data-ttu-id="3f400-102">文件适配器属性架构和属性</span><span class="sxs-lookup"><span data-stu-id="3f400-102">File adapter property schema and properties</span></span>
<span data-ttu-id="3f400-103">下表包含文件适配器属性架构中的属性。</span><span class="sxs-lookup"><span data-stu-id="3f400-103">The following table contains the properties in the File adapter property schema.</span></span>  
  
 <span data-ttu-id="3f400-104">**Namespace:** http://schemas.microsoft.com/BizTalk/2003/file-properties</span><span class="sxs-lookup"><span data-stu-id="3f400-104">**Namespace:** http://schemas.microsoft.com/BizTalk/2003/file-properties</span></span>  
  
|<span data-ttu-id="3f400-105">Name</span><span class="sxs-lookup"><span data-stu-id="3f400-105">Name</span></span>|<span data-ttu-id="3f400-106">类型</span><span class="sxs-lookup"><span data-stu-id="3f400-106">Type</span></span>|<span data-ttu-id="3f400-107">Description</span><span class="sxs-lookup"><span data-stu-id="3f400-107">Description</span></span>|  
|----------|----------|-----------------|  
|<span data-ttu-id="3f400-108">**CopyMode**</span><span class="sxs-lookup"><span data-stu-id="3f400-108">**CopyMode**</span></span>|<span data-ttu-id="3f400-109">xs:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="3f400-109">xs:unsignedInt</span></span>|<span data-ttu-id="3f400-110">定义向文件中写入消息时使用的复制模式。</span><span class="sxs-lookup"><span data-stu-id="3f400-110">Defines the copy mode to use when writing a message to a file.</span></span> <span data-ttu-id="3f400-111">有效值为</span><span class="sxs-lookup"><span data-stu-id="3f400-111">Valid values are:</span></span><br /><br /> <span data-ttu-id="3f400-112">**追加 (0)。**</span><span class="sxs-lookup"><span data-stu-id="3f400-112">**Append (0).**</span></span> <span data-ttu-id="3f400-113">文件发送处理程序打开一个文件（如果该文件存在）并在该文件末尾附加一个消息。</span><span class="sxs-lookup"><span data-stu-id="3f400-113">The File send handler opens a file if it exists and appends a message to the end of the file.</span></span> <span data-ttu-id="3f400-114">如果文件不存在，则文件发送处理程序将创建一个新文件。</span><span class="sxs-lookup"><span data-stu-id="3f400-114">If the file does not exist, the File send handler creates a new file.</span></span><br /><br /> <span data-ttu-id="3f400-115">**创建新的 (1)。**</span><span class="sxs-lookup"><span data-stu-id="3f400-115">**Create new (1).**</span></span> <span data-ttu-id="3f400-116">如果文件不存在，则文件发送处理程序将创建一个新文件，并在该文件中写入消息。</span><span class="sxs-lookup"><span data-stu-id="3f400-116">If a file does not exist, the File send handler creates a new file and writes to it.</span></span> <span data-ttu-id="3f400-117">如果该文件已存在，则文件发送处理程序将报告错误，然后按照发送端口的通用适配器重试逻辑操作。</span><span class="sxs-lookup"><span data-stu-id="3f400-117">If the file already exists, the File send handler reports an error and then follows common adapter retry logic for send ports.</span></span> <span data-ttu-id="3f400-118">此模式为文件发送处理程序的默认复制模式。</span><span class="sxs-lookup"><span data-stu-id="3f400-118">This is a default copy mode for the File send handler.</span></span><br /><br /> <span data-ttu-id="3f400-119">**覆盖 (2)。**</span><span class="sxs-lookup"><span data-stu-id="3f400-119">**Overwrite (2).**</span></span> <span data-ttu-id="3f400-120">文件发送处理程序打开一个文件（如果该文件存在）并覆盖其内容。</span><span class="sxs-lookup"><span data-stu-id="3f400-120">The File send handler opens a file if it exists and overwrites its content.</span></span> <span data-ttu-id="3f400-121">如果文件不存在，则文件发送处理程序将创建一个新文件。</span><span class="sxs-lookup"><span data-stu-id="3f400-121">If the file does not exist, the File send handler creates a new file.</span></span>|  
|<span data-ttu-id="3f400-122">**AllowCacheOnWrite**</span><span class="sxs-lookup"><span data-stu-id="3f400-122">**AllowCacheOnWrite**</span></span>|<span data-ttu-id="3f400-123">xs:Boolean</span><span class="sxs-lookup"><span data-stu-id="3f400-123">xs:Boolean</span></span>|<span data-ttu-id="3f400-124">定义文件适配器在向文件中写入消息时是否使用文件系统缓存。</span><span class="sxs-lookup"><span data-stu-id="3f400-124">Defines whether the File adapter uses file system caching when writing messages to a file.</span></span>|  
|<span data-ttu-id="3f400-125">**ReceivedFileName**</span><span class="sxs-lookup"><span data-stu-id="3f400-125">**ReceivedFileName**</span></span>|<span data-ttu-id="3f400-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="3f400-126">xs:string</span></span>|<span data-ttu-id="3f400-127">定义文件适配器从中读取消息的文件的全名。</span><span class="sxs-lookup"><span data-stu-id="3f400-127">Defines the full name of the file from which the File adapter reads the message.</span></span>|  
|<span data-ttu-id="3f400-128">**FileCreationTime**</span><span class="sxs-lookup"><span data-stu-id="3f400-128">**FileCreationTime**</span></span>|<span data-ttu-id="3f400-129">xs:datetime</span><span class="sxs-lookup"><span data-stu-id="3f400-129">xs:datetime</span></span>|<span data-ttu-id="3f400-130">定义将文件写入文件接收适配器所监视的文件夹的时间。</span><span class="sxs-lookup"><span data-stu-id="3f400-130">Defines the time that the file was written to the folder that is monitored by the File receive adapter.</span></span>|  
|<span data-ttu-id="3f400-131">**用户名**</span><span class="sxs-lookup"><span data-stu-id="3f400-131">**Username**</span></span>|<span data-ttu-id="3f400-132">xs:string</span><span class="sxs-lookup"><span data-stu-id="3f400-132">xs:string</span></span>|<span data-ttu-id="3f400-133">定义在指定用于访问网络共享位置的备用凭据时所用帐户的用户名。</span><span class="sxs-lookup"><span data-stu-id="3f400-133">Defines the user name for the account used when specifying alternative credentials to access a network share.</span></span>|  
|<span data-ttu-id="3f400-134">**密码**</span><span class="sxs-lookup"><span data-stu-id="3f400-134">**Password**</span></span>|<span data-ttu-id="3f400-135">xs:string</span><span class="sxs-lookup"><span data-stu-id="3f400-135">xs:string</span></span>|<span data-ttu-id="3f400-136">定义在指定用于访问网络共享位置的备用凭据时所用帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="3f400-136">Defines the password for the account used when specifying alternative credentials to access a network share.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3f400-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3f400-137">See Also</span></span>  
 [<span data-ttu-id="3f400-138">配置文件适配器</span><span class="sxs-lookup"><span data-stu-id="3f400-138">Configuring the File Adapter</span></span>](../core/configure-the-file-adapter.md)