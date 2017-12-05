---
title: "错误提取程序示例类 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Error Extractor Sample class
- errors, Error Extractor Sample class
ms.assetid: d0d59b21-d80a-4466-a77a-1d3b7df1bc2a
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 53ceb305dcd30164e385022f66140fcaa626b133
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="error-extractor-sample-class"></a><span data-ttu-id="02fe5-102">错误提取程序示例类</span><span class="sxs-lookup"><span data-stu-id="02fe5-102">Error Extractor Sample Class</span></span>
<span data-ttu-id="02fe5-103">[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]反汇编程序序列化将错误记录到 XML 对象，并将 XML 对象附加到多部分消息的错误部分。</span><span class="sxs-lookup"><span data-stu-id="02fe5-103">The [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] disassembler serializes errors to an XML object, and attaches the XML object to the error section of a multipart message.</span></span> <span data-ttu-id="02fe5-104">反汇编程序随后会在失败的消息发布到 MessageBox 数据库就像将有效的消息。</span><span class="sxs-lookup"><span data-stu-id="02fe5-104">The disassembler then publishes the failed message to the MessageBox database just as it would a valid message.</span></span> <span data-ttu-id="02fe5-105">因此，到 MessageBox 数据库失败消息包含错误详细信息。</span><span class="sxs-lookup"><span data-stu-id="02fe5-105">Therefore, failed messages carry error details into the MessageBox database.</span></span> <span data-ttu-id="02fe5-106">可以使用错误提取程序示例类从失败的消息，提取错误详细信息，并生成一个文件具有错误详细信息，并具有原始消息的另一个文件。</span><span class="sxs-lookup"><span data-stu-id="02fe5-106">You can use the Error Extractor Sample Class to extract the error details from a failed message, and generate one file that has the error details and another file that has the original message.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="02fe5-107">错误提取程序示例类是 SDK 中的示例代码。</span><span class="sxs-lookup"><span data-stu-id="02fe5-107">The Error Extractor Sample Class is sample code in the SDK.</span></span> <span data-ttu-id="02fe5-108">它不用于在生产中使用。</span><span class="sxs-lookup"><span data-stu-id="02fe5-108">It is not intended for use in production.</span></span>  
  
 <span data-ttu-id="02fe5-109">若要使用错误提取程序示例类，必须创建业务流程来处理失败的消息。</span><span class="sxs-lookup"><span data-stu-id="02fe5-109">To use the Error Extractor Sample Class, you must create an orchestration to process the failed message.</span></span> <span data-ttu-id="02fe5-110">此业务流程包括步骤以提取失败消息的正文，提取的错误部分的失败的消息，然后编写正文和错误部分以单独的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="02fe5-110">This orchestration includes steps to extract the body of the failed message, extract the error part of the failed message, and then write the body and the error part to separate XML files.</span></span> <span data-ttu-id="02fe5-111">业务流程将表示每个步骤中调用错误提取程序示例类中的一个或多个以下方法的表达式阶段：</span><span class="sxs-lookup"><span data-stu-id="02fe5-111">The orchestration represents each of these steps in an expression stage that calls one or more of the following methods in the Error Extractor Sample Class:</span></span>  
  
## <a name="getbodypartasstring-method"></a><span data-ttu-id="02fe5-112">GetBodyPartAsString 方法</span><span class="sxs-lookup"><span data-stu-id="02fe5-112">GetBodyPartAsString method</span></span>  
 <span data-ttu-id="02fe5-113">此方法返回一个字符串，包含的 XML 在 XLANG 消息 xm 的正文部分中找到。</span><span class="sxs-lookup"><span data-stu-id="02fe5-113">This method returns a string that contains the XML found in the body part of the XLANG message 'xm'.</span></span> <span data-ttu-id="02fe5-114">方法需要包含正文部分的 XLANG 消息 xm 调用"BodySegment。"</span><span class="sxs-lookup"><span data-stu-id="02fe5-114">The method expects the XLANG message 'xm' to contain a body part called "BodySegment."</span></span> <span data-ttu-id="02fe5-115">因此，您必须声明 xm 中具有同名正文一部分调用的业务流程。</span><span class="sxs-lookup"><span data-stu-id="02fe5-115">Therefore, you must declare 'xm' in the calling orchestration with this body part name.</span></span> <span data-ttu-id="02fe5-116">如果"BodySegment"不存在 xm 的一部分**GetBodyPartAsString**引发异常。</span><span class="sxs-lookup"><span data-stu-id="02fe5-116">If "BodySegment" does not exist as a part of 'xm', **GetBodyPartAsString** throws an exception.</span></span>  
  
```  
SWIFTErrorExtractor.ErrorExtractor.GetBodyPartAsString(XLANGMessage xm);  
```  
  
## <a name="geterrorpartasstring-method"></a><span data-ttu-id="02fe5-117">GetErrorPartAsString 方法</span><span class="sxs-lookup"><span data-stu-id="02fe5-117">GetErrorPartAsString method</span></span>  
 <span data-ttu-id="02fe5-118">此方法返回一个字符串，包含的 XML 在 XLANG 消息 xm 的错误部分中找到。</span><span class="sxs-lookup"><span data-stu-id="02fe5-118">This method returns a string that contains the XML found in the error part of the XLANG message 'xm'.</span></span> <span data-ttu-id="02fe5-119">方法需要包含一个错误部分的 XLANG 消息 xm 调用"ErrorSegment。"</span><span class="sxs-lookup"><span data-stu-id="02fe5-119">The method expects the XLANG message 'xm' to contain an error part called "ErrorSegment."</span></span> <span data-ttu-id="02fe5-120">因此，您必须声明 xm 中具有同名错误一部分调用的业务流程。</span><span class="sxs-lookup"><span data-stu-id="02fe5-120">Therefore, you must declare 'xm' in the calling orchestration with this error part name.</span></span> <span data-ttu-id="02fe5-121">如果"ErrorSegment"不存在 xm 的一部分**GetErrorPartAsString**引发异常。</span><span class="sxs-lookup"><span data-stu-id="02fe5-121">If "ErrorSegment" does not exist as a part of 'xm', **GetErrorPartAsString** throws an exception.</span></span>  
  
```  
SWIFTErrorExtractor.ErrorExtractor.GetErrorPartAsString(XLANGMessage xm);  
```  
  
## <a name="writetofile-method"></a><span data-ttu-id="02fe5-122">WriteToFile 方法</span><span class="sxs-lookup"><span data-stu-id="02fe5-122">WriteToFile method</span></span>  
 <span data-ttu-id="02fe5-123">此方法将写入从字符串*消息*参数指定的文件*filePath*参数。</span><span class="sxs-lookup"><span data-stu-id="02fe5-123">This method writes the string from the *message* parameter to the file specified by the *filePath* parameter.</span></span>  
  
```  
SWIFTErrorExtractor.ErrorExtractor.WriteToFile(string filePath, string message);  
```  
  
 <span data-ttu-id="02fe5-124">A4SWIFT 安装程序安装错误提取程序示例类 (SWIFTErrorExtractor.dll) 作为中 A4SWIFT SDK 的一部分\<*驱动器*\>: files\microsoft BizTalk Accelerator for SWIFT\SDK\Tutorial\SWIFTErrorExtractor。</span><span class="sxs-lookup"><span data-stu-id="02fe5-124">A4SWIFT Setup installs the Error Extractor Sample Class (SWIFTErrorExtractor.dll) as part of the A4SWIFT SDK in \<*drive*\>:\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tutorial\SWIFTErrorExtractor.</span></span> <span data-ttu-id="02fe5-125">此文件夹还包括示例类 (ErrorExtractor.cs) 的源代码。</span><span class="sxs-lookup"><span data-stu-id="02fe5-125">This folder also includes the source code for the sample class (ErrorExtractor.cs).</span></span>  
  
 <span data-ttu-id="02fe5-126">若要从业务流程调用 SWIFTErrorExtractor.dll，必须将.dll 文件发布到全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="02fe5-126">To call SWIFTErrorExtractor.dll from the orchestration, you must publish the .dll file to the global assembly cache.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02fe5-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="02fe5-127">See Also</span></span>  
 [<span data-ttu-id="02fe5-128">工具</span><span class="sxs-lookup"><span data-stu-id="02fe5-128">Tools</span></span>](../../adapters-and-accelerators/accelerator-swift/tools.md)