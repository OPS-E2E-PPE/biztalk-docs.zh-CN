---
title: 扩展平面文件反汇编程序管道组件 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, code sample
- pipeline components [custom], flat file documents
- pipeline components [custom], disassembling
ms.assetid: 4bcc746a-696a-4e5c-be01-f8409fce21fa
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 031189c0ecadfd8a7baff38200f044598e800437
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246229"
---
# <a name="extending-the-flat-file-disassembler-pipeline-component"></a><span data-ttu-id="9420c-102">扩展平面文件反汇编程序管道组件</span><span class="sxs-lookup"><span data-stu-id="9420c-102">Extending the Flat File Disassembler Pipeline Component</span></span>
<span data-ttu-id="9420c-103">下面的示例演示如何创建自定义拆装器以便解析用 UTF-7 编码的平面文件文档。</span><span class="sxs-lookup"><span data-stu-id="9420c-103">The following sample illustrates how to create a custom disassembler to parse flat file documents that are UTF-7 encoded.</span></span> <span data-ttu-id="9420c-104">若要处理 utf-7 文档，该组件，继承自**FFDasmComp**类，然后并重写其**GetDataReader**方法。</span><span class="sxs-lookup"><span data-stu-id="9420c-104">To process UTF-7 documents, the component inherits from the **FFDasmComp** class and then overrides its **GetDataReader** method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9420c-105">示例</span><span class="sxs-lookup"><span data-stu-id="9420c-105">Example</span></span>  
  
```  
using System;  
using System.Text;  
using System.IO;  
using Microsoft.BizTalk.Message.Interop;  
using Microsoft.BizTalk.Component.Interop;  
using Microsoft.BizTalk.ParsingEngine;  
using Microsoft.BizTalk.Component;  
using System.Runtime.InteropServices;  
  
namespace Microsoft.BizTalk.Test  
{  
   /// <summary>  
   /// Implements FF disassembler which always uses UTF-7 encoding.  
   /// </summary>  
   [ComponentCategory(CategoryTypes.CATID_PipelineComponent)]  
   [ComponentCategory(CategoryTypes.CATID_DisassemblingParser)]  
   [ComponentCategory(CategoryTypes.CATID_Streamer)]  
   [Guid("A6E5F54F-7902-4e1a-84D8-5C7584F0ECF2")]  
   public class Utf7FFDasm :   
      FFDasmComp,  
      IBaseComponent  
   {  
      /// <summary>  
      /// Initializes a Utf7FFAsmDasm instance.  
      /// </summary>  
      public Utf7FFDasm()  
      {  
      }  
  
      /// <summary>  
      /// Name property  
      /// </summary>  
      public new string Name   
      {  
         get   
         {  
            return "UTF-7 FlatFile Disassembler";  
         }  
      }  
  
      /// <summary>  
      /// Version property  
      /// </summary>  
      public new string Version   
      {  
         get   
         {  
            return "1.0";  
         }  
      }  
  
      /// <summary>  
      /// Description property  
      /// </summary>  
      public new string Description   
      {  
         get   
         {  
            return "UTF-7 FlatFile Disassembler";  
         }  
      }  
  
      /// <summary>  
      /// Gets a data reader instance  
      /// </summary>  
      /// <param name="dataStream">Data stream</param>  
      /// <param name="dataEncoding">Data encoding</param>  
      /// <param name="detectEncodingFromByteOrderMarks">Detect encoding from a byte order mark</param>  
      /// <returns>IDataReader instance</returns>  
      protected override IDataReader GetDataReader(Stream dataStream, Encoding dataEncoding, bool detectEncodingFromByteOrderMarks)  
      {  
         // Delegate call to the base implementation passing fixed UTF-7 encoding  
            return base.GetDataReader(dataStream, Encoding.UTF7, false);  
      }  
   }  
}  
```  
  
## <a name="example"></a><span data-ttu-id="9420c-106">示例</span><span class="sxs-lookup"><span data-stu-id="9420c-106">Example</span></span>  
 <span data-ttu-id="9420c-107">下面的示例演示如何创建自定义拆装器以便执行平面文件交换的事务处理。</span><span class="sxs-lookup"><span data-stu-id="9420c-107">The following example illustrates how to create a custom disassembler for transactional processing of flat file interchanges.</span></span> <span data-ttu-id="9420c-108">自定义拆装器与标准平面文件拆装器的不同之处在于：前者在整个输入交换都完全处理前，并不生成任何已拆装的文档。</span><span class="sxs-lookup"><span data-stu-id="9420c-108">It differs from the standard Flat File Disassembler in that it does not produce any disassembled documents until the entire input interchange is completely processed.</span></span> <span data-ttu-id="9420c-109">此组件实现继承自**FFDasmComp**类，并重写**GetNext**方法。</span><span class="sxs-lookup"><span data-stu-id="9420c-109">This component implementation inherits from the **FFDasmComp** class and overrides the **GetNext** method.</span></span> <span data-ttu-id="9420c-110">在第一个调用**GetNext**方法，它会处理所有消息交换中的，将它们存储在**ArrayList**，并返回从第一条消息**ArrayList**。</span><span class="sxs-lookup"><span data-stu-id="9420c-110">On the first call to the **GetNext** method, it processes all messages in the interchange, stores them in an **ArrayList**, and returns the first message from the **ArrayList**.</span></span> <span data-ttu-id="9420c-111">后续调用中，它将返回从下一条消息**ArrayList**。</span><span class="sxs-lookup"><span data-stu-id="9420c-111">On subsequent calls, it returns the next message from the **ArrayList**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9420c-112">在下面的代码示例中实现 GetNext() 方法的方式并不适合于处理大型文档，因为它将在内存中保留整个交换。</span><span class="sxs-lookup"><span data-stu-id="9420c-112">The implementation of the GetNext() method in the code sample below would not be suitable for the processing of large documents because it retains the entire interchange in memory.</span></span>  <span data-ttu-id="9420c-113">将此技术用于大型文档可能会用尽内存资源，从而导致性能下降或出现不稳定的行为。</span><span class="sxs-lookup"><span data-stu-id="9420c-113">Using this technique for large documents could exhaust memory resources and cause degraded performance or unstable behavior.</span></span>  
  
```  
using System;  
using System.Collections;  
using System.Runtime.InteropServices;  
using Microsoft.BizTalk.Message.Interop;  
using Microsoft.BizTalk.Component.Interop;  
using Microsoft.BizTalk.Component;  
  
namespace Microsoft.BizTalk.Component  
{  
   /// <summary>  
   /// Summary description for Class1.  
   /// </summary>  
   [ComponentCategory(CategoryTypes.CATID_PipelineComponent)]  
   [ComponentCategory(CategoryTypes.CATID_DisassemblingParser)]  
   [Guid("EB4714A8-FD97-43de-84E2-E011648F349B")]  
   public class TransactionalFFDasm :   
      FFDasmComp,  
      IBaseComponent,  
      IDisassemblerComponent  
   {  
      public TransactionalFFDasm()  
      {  
      }  
  
      #region IBaseComponent Members  
  
      public new string Description  
      {  
         get  
         {  
            return "Transactional Flat File Disassembler";  
         }  
      }  
  
      public new string Name  
      {  
         get  
         {  
            return "Transactional Flat File Disassembler";  
         }  
      }  
  
      public new string Version  
      {  
         get  
         {  
            return "1.0";  
         }  
      }  
  
      #endregion  
  
      #region IDisassemblerComponent Members  
  
      public new void Disassemble(IPipelineContext pContext, IBaseMessage pInMsg)  
      {  
         base.Disassemble(pContext, pInMsg);  
      }  
  
      public new IBaseMessage GetNext(IPipelineContext pContext)  
      {  
         // Check if don't need to stop collecting messages  
         if (currentMessage == 0)  
         {  
            messageInterchange = new ArrayList();  
            currentMessage = 0;  
  
            // Collect messages from the standard disassembler  
            IBaseMessage disassembledMessage = null;  
            while ((disassembledMessage = base.GetNext(pContext)) != null)  
            {  
               byte[] buffer = new byte[4096];  
               int count = 0;  
  
               // Create a new memory stream to contain the disassembled message.  
               MemoryStream messageStream = new MemoryStream();  
  
               // Get a stream pointer to the disassembled stream.  
               Stream disassembledStream = disassembledMessage.BodyPart.GetOriginalDataStream();  
  
               // Write the disassembled message to the memory stream  
               while (0 != (count == disassembledStream.Read(buffer, 0, 4096)))  
               {  
                  messageStream.Write(buffer, 0, count);  
               } // end-while  
  
               // Rewind the stream to the beginning  
               messageStream.Seek(0, SeekOrigin.Begin);  
  
               // Replace the stream on the disassembled message with the memory stream.  
               disassembledMessage.BodyPart.data = messageStream;  
  
               // Add this message to the ArrayList of messages.  
               messageInterchange.Add(disassembledMessage);  
            } // end-while  
  
            // Check if no messages were collected, just return nothing  
            if (0 == messageInterchange.Count)  
               return null;  
         } // end-if  
  
         // Check if all collected messages are returned  
         if (currentMessage == messageInterchange.Count)  
            return null;  
  
         // Return the current collected message  
         return (IBaseMessage)messageInterchange[currentMessage++];  
      } // end-method GetNext()  
  
      #endregion  
  
      private ArrayList messageInterchange = null;  
      private int currentMessage = 0;  
   }  
}  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="9420c-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9420c-114">See Also</span></span>  
 [<span data-ttu-id="9420c-115">开发分解的管道组件</span><span class="sxs-lookup"><span data-stu-id="9420c-115">Developing a Disassembling Pipeline Component</span></span>](../core/developing-a-disassembling-pipeline-component.md)