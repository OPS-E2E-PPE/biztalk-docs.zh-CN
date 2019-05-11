---
title: 错误提取程序示例类 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Error Extractor Sample class
- errors, Error Extractor Sample class
ms.assetid: d0d59b21-d80a-4466-a77a-1d3b7df1bc2a
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26375519e77de07161e20d9e373f2382cdbf0aac
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378009"
---
# <a name="error-extractor-sample-class"></a><span data-ttu-id="85787-102">错误提取程序示例类</span><span class="sxs-lookup"><span data-stu-id="85787-102">Error Extractor Sample Class</span></span>
<span data-ttu-id="85787-103">Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]拆装器序列化将错误记录到 XML 对象，并将 XML 对象附加到多部分消息的错误部分。</span><span class="sxs-lookup"><span data-stu-id="85787-103">The Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] disassembler serializes errors to an XML object, and attaches the XML object to the error section of a multipart message.</span></span> <span data-ttu-id="85787-104">拆装器就像一样是有效的消息，然后将失败的消息发布到 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="85787-104">The disassembler then publishes the failed message to the MessageBox database just as it would a valid message.</span></span> <span data-ttu-id="85787-105">因此，失败消息携带错误详细信息到 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="85787-105">Therefore, failed messages carry error details into the MessageBox database.</span></span> <span data-ttu-id="85787-106">可以使用错误提取程序示例类从失败的消息，提取错误详细信息，并生成一个文件包含错误详细信息，并具有原始消息的另一个文件。</span><span class="sxs-lookup"><span data-stu-id="85787-106">You can use the Error Extractor Sample Class to extract the error details from a failed message, and generate one file that has the error details and another file that has the original message.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="85787-107">错误提取程序示例类是在 SDK 中的示例代码。</span><span class="sxs-lookup"><span data-stu-id="85787-107">The Error Extractor Sample Class is sample code in the SDK.</span></span> <span data-ttu-id="85787-108">它不适合在生产中使用。</span><span class="sxs-lookup"><span data-stu-id="85787-108">It is not intended for use in production.</span></span>  
  
 <span data-ttu-id="85787-109">若要使用错误提取程序示例类，必须创建业务流程来处理失败的消息。</span><span class="sxs-lookup"><span data-stu-id="85787-109">To use the Error Extractor Sample Class, you must create an orchestration to process the failed message.</span></span> <span data-ttu-id="85787-110">此业务流程包括失败消息的正文提取、 提取失败消息的错误部分，然后编写的正文和错误部分以单独的 XML 文件的步骤。</span><span class="sxs-lookup"><span data-stu-id="85787-110">This orchestration includes steps to extract the body of the failed message, extract the error part of the failed message, and then write the body and the error part to separate XML files.</span></span> <span data-ttu-id="85787-111">该业务流程表示每个步骤中的表达式阶段错误提取程序示例类中调用一个或多个以下方法：</span><span class="sxs-lookup"><span data-stu-id="85787-111">The orchestration represents each of these steps in an expression stage that calls one or more of the following methods in the Error Extractor Sample Class:</span></span>  
  
## <a name="getbodypartasstring-method"></a><span data-ttu-id="85787-112">GetBodyPartAsString 方法</span><span class="sxs-lookup"><span data-stu-id="85787-112">GetBodyPartAsString method</span></span>  
 <span data-ttu-id="85787-113">此方法返回一个字符串，包含的 XML 在 XLANG 消息 xm 的正文部分中找到。</span><span class="sxs-lookup"><span data-stu-id="85787-113">This method returns a string that contains the XML found in the body part of the XLANG message 'xm'.</span></span> <span data-ttu-id="85787-114">该方法需要包含一个正文部分 XLANG 消息 xm 调用"BodySegment。"</span><span class="sxs-lookup"><span data-stu-id="85787-114">The method expects the XLANG message 'xm' to contain a body part called "BodySegment."</span></span> <span data-ttu-id="85787-115">因此，您必须声明 xm 在调用业务流程中使用此正文部分名称。</span><span class="sxs-lookup"><span data-stu-id="85787-115">Therefore, you must declare 'xm' in the calling orchestration with this body part name.</span></span> <span data-ttu-id="85787-116">如果"BodySegment"不存在 xm 的一部分**GetBodyPartAsString**将引发异常。</span><span class="sxs-lookup"><span data-stu-id="85787-116">If "BodySegment" does not exist as a part of 'xm', **GetBodyPartAsString** throws an exception.</span></span>  
  
```  
SWIFTErrorExtractor.ErrorExtractor.GetBodyPartAsString(XLANGMessage xm);  
```  
  
## <a name="geterrorpartasstring-method"></a><span data-ttu-id="85787-117">GetErrorPartAsString 方法</span><span class="sxs-lookup"><span data-stu-id="85787-117">GetErrorPartAsString method</span></span>  
 <span data-ttu-id="85787-118">此方法返回 XLANG 消息 xm 的错误部分中找到包含的 XML 字符串。</span><span class="sxs-lookup"><span data-stu-id="85787-118">This method returns a string that contains the XML found in the error part of the XLANG message 'xm'.</span></span> <span data-ttu-id="85787-119">该方法需要包含一个错误部分 XLANG 消息 xm 调用"ErrorSegment。"</span><span class="sxs-lookup"><span data-stu-id="85787-119">The method expects the XLANG message 'xm' to contain an error part called "ErrorSegment."</span></span> <span data-ttu-id="85787-120">因此，您必须声明 xm 在调用业务流程中使用此错误部分名称。</span><span class="sxs-lookup"><span data-stu-id="85787-120">Therefore, you must declare 'xm' in the calling orchestration with this error part name.</span></span> <span data-ttu-id="85787-121">如果"ErrorSegment"不存在 xm 的一部分**GetErrorPartAsString**将引发异常。</span><span class="sxs-lookup"><span data-stu-id="85787-121">If "ErrorSegment" does not exist as a part of 'xm', **GetErrorPartAsString** throws an exception.</span></span>  
  
```  
SWIFTErrorExtractor.ErrorExtractor.GetErrorPartAsString(XLANGMessage xm);  
```  
  
## <a name="writetofile-method"></a><span data-ttu-id="85787-122">WriteToFile 方法</span><span class="sxs-lookup"><span data-stu-id="85787-122">WriteToFile method</span></span>  
 <span data-ttu-id="85787-123">此方法将从字符串写入*消息*参数指定的文件*filePath*参数。</span><span class="sxs-lookup"><span data-stu-id="85787-123">This method writes the string from the *message* parameter to the file specified by the *filePath* parameter.</span></span>  
  
```  
SWIFTErrorExtractor.ErrorExtractor.WriteToFile(string filePath, string message);  
```  
  
 <span data-ttu-id="85787-124">A4SWIFT 安装程序安装错误提取程序示例类 (SWIFTErrorExtractor.dll) 在 A4SWIFT SDK 的一部分\<*驱动器*\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tutorial\SWIFTErrorExtractor。</span><span class="sxs-lookup"><span data-stu-id="85787-124">A4SWIFT Setup installs the Error Extractor Sample Class (SWIFTErrorExtractor.dll) as part of the A4SWIFT SDK in \<*drive*\>:\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tutorial\SWIFTErrorExtractor.</span></span> <span data-ttu-id="85787-125">此文件夹还包括示例类 (ErrorExtractor.cs) 的源代码。</span><span class="sxs-lookup"><span data-stu-id="85787-125">This folder also includes the source code for the sample class (ErrorExtractor.cs).</span></span>  
  
 <span data-ttu-id="85787-126">若要从业务流程调用 SWIFTErrorExtractor.dll，必须将.dll 文件发布到全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="85787-126">To call SWIFTErrorExtractor.dll from the orchestration, you must publish the .dll file to the global assembly cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85787-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="85787-127">See Also</span></span>  
 [<span data-ttu-id="85787-128">工具</span><span class="sxs-lookup"><span data-stu-id="85787-128">Tools</span></span>](../../adapters-and-accelerators/accelerator-swift/tools.md)