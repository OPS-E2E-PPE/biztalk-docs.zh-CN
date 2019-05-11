---
title: 创建消息实例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d75cb744-99a0-44bc-9a84-d4f8f66fd97e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 708939189ea11e40752a6bff08e4ce850553207d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65251329"
---
# <a name="create-the-message-instances"></a><span data-ttu-id="37db4-102">创建消息实例</span><span class="sxs-lookup"><span data-stu-id="37db4-102">Create the Message Instances</span></span>
<span data-ttu-id="37db4-103">若要创建 ADT^A03.txt 消息文件，并创建你将需要运行批处理教程时要使用的消息实例，请使用以下过程。</span><span class="sxs-lookup"><span data-stu-id="37db4-103">Use the following procedures to create the ADT^A03.txt message file, and to create the message instances that you will need to use when you run the Batching tutorial.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="37db4-104">在记事本中创建这些消息，当删除回车符后的最后一行。</span><span class="sxs-lookup"><span data-stu-id="37db4-104">When creating these messages in Notepad, delete the carriage return following the last line.</span></span>  
  
### <a name="to-create-the-fragmented-batch-message-instance-text-file"></a><span data-ttu-id="37db4-105">若要创建零碎的批处理消息实例的文本文件</span><span class="sxs-lookup"><span data-stu-id="37db4-105">To create the fragmented batch message instance text file</span></span>  
  
1.  <span data-ttu-id="37db4-106">打开记事本。</span><span class="sxs-lookup"><span data-stu-id="37db4-106">Open Notepad.</span></span>  
  
2.  <span data-ttu-id="37db4-107">将以下文本复制到记事本：</span><span class="sxs-lookup"><span data-stu-id="37db4-107">Copy the following text into Notepad:</span></span>  
  
    ```  
    FHS|^~\&|Tutorial_BatchSource|FileSendingFacility|Tutorial_BatchParty|FileReceivingFacility|20040215115056.2222-0800  
    BHS|^~\&|Tutorial_BatchSource|BatchSendingFacility|Tutorial_BatchParty|BatchReceivingFacility|20040215115056.2222-0800  
    MSH|^~\&|Tutorial_BatchSource|XYZ_ADMITTING|MESA_IS|XYZ_HOSPITAL|20040215115056||ADT^A03|000001|P|2.3.1  
    EVN|A03|199601121005||01||199601121000  
    PID|||191919^^^MYHOS^MR~123-45-6789^^^USSSA^SS|253763|SMITH^JOHN^Q||19560129|M|||123MAIN^^BUFFALO^NY^98052^""||(123)555-0100||S|M|10199925^^^MYHOS^AN|123-45-6789  
    PD1|S|F|NormalString^A^+1^-1^ISO^simpletext&Test&HCD^GI^simpletext&NormalString&ISO^I|NormalString^Test&Test^Test^Test^Test^Test^AE^simpletext^simpletext&Test&ISO^P^NormalString^M10^MC^simpletext&NormalString&HCD^A|N|simpletext|I|I|N|NormalString^+1^M11^simpletext&NormalString&L,M,N^RRI^simpletext&NormalString&HCD|NOVALUE^NormalString^Test^Test^NormalString^Test|N  
    PV1|1|I|2000^2012^01^hey&test&DNS^test^test^test^test^test||||004777^MILLER^CONNIE^A.|||SUR||||2|A0  
    MSH|^~\&|Tutorial_BatchSource|XYZ_ADMITTING|MESA_IS|XYZ_HOSPITAL|20040215115056||ADT^A03|000002|T|2.3.1  
    EVN|A03|199601121005||01||199601121000  
    PID|||191919^^^MYHOS^MR~123-45-6789^^^USSSA^SS|253763|DOE^JOHN||19560129|M|||123MAIN^^BUFFALO^NY^98052^""||(123)555-0100||S|M|10199925^^^MYHOS^AN|123-45-6789  
    PD1|S|F|String^A^+1^-1^ISO^simpletext&Test&HCD^GI^simpletext&NormalString&ISO^I|NormalString^Test&Test^Test^Test^Test^Test^AE^simpletext^simpletext&Test&ISO^P^NormalString^M10^MC^simpletext&NormalString&HCD^A|N|simpletext|I|I|N|NormalString^+1^M11^simpletext&NormalString&L,M,N^RRI^simpletext&NormalString&HCD|NOVALUE^NormalString^Test^Test^NormalString^Test|N  
    PV1|1|I|2000^2012^01^JDL&test&DNS^test^test^test^test^test||||004777^DOE^JANE^A.|||SUR||||2|A0  
    BTS|2|Batch,MessageCount,Comment,Totals|2  
    FTS|1|File,BatchCount,TrailerComment  
    ```  
  
3.  <span data-ttu-id="37db4-108">将该文件作为**FragmentedInboundBatch.txt**中\<*驱动器*:\>\Batching Tutorial\Instances 文件夹，然后关闭记事本。</span><span class="sxs-lookup"><span data-stu-id="37db4-108">Save the file as **FragmentedInboundBatch.txt** in the \<*drive*:\>\Batching Tutorial\Instances folder, and then close Notepad.</span></span>  
  
### <a name="to-create-the-batch-inbatch-out-message-instance-text-file"></a><span data-ttu-id="37db4-109">若要创建在批处理 / 出消息实例文本文件批处理</span><span class="sxs-lookup"><span data-stu-id="37db4-109">To create the batch in/batch out message instance text file</span></span>  
  
1.  <span data-ttu-id="37db4-110">打开记事本。</span><span class="sxs-lookup"><span data-stu-id="37db4-110">Open Notepad.</span></span>  
  
2.  <span data-ttu-id="37db4-111">将以下文本复制到记事本：</span><span class="sxs-lookup"><span data-stu-id="37db4-111">Copy the following text into Notepad:</span></span>  
  
    ```  
    MSH|^~\&|Tutorial_BatchSource|XYZ_ADMITTING|MESA_IS|XYZ_HOSPITAL|20040215115056||ADT^A03|000001|P|2.3.1  
    EVN|A03|199601121005||01||199601121000  
    PID|||191919^^^MYHOS^MR~123-45-6789^^^USSSA^SS|253763|SMITH^JOHN^Q||19560129|M|||123MAIN^^BUFFALO^NY^98052^""||(123)555-0100||S|M|10199925^^^MYHOS^AN|123-45-6789  
    PD1|S|F|NormalString^A^+1^-1^ISO^simpletext&Test&HCD^GI^simpletext&NormalString&ISO^I|NormalString^Test&Test^Test^Test^Test^Test^AE^simpletext^simpletext&Test&ISO^P^NormalString^M10^MC^simpletext&NormalString&HCD^A|N|simpletext|I|I|N|NormalString^+1^M11^simpletext&NormalString&L,M,N^RRI^simpletext&NormalString&HCD|NOVALUE^NormalString^Test^Test^NormalString^Test|N  
    PV1|1|I|2000^2012^01^hey&test&DNS^test^test^test^test^test||||004777^MILLER^CONNIE^A.|||SUR||||2|A0  
    MSH|^~\&|Tutorial_BatchSource|XYZ_ADMITTING|MESA_IS|XYZ_HOSPITAL|20040215115056||ADT^A03|000002|T|2.3.1  
    EVN|A03|199601121005||01||199601121000  
    PID|||191919^^^MYHOS^MR~123-45-6789^^^USSSA^SS|253763|DOE^JOHN||19560129|M|||123MAIN^^BUFFALO^NY^98052^""||(123)555-0100||S|M|10199925^^^MYHOS^AN|123-45-6789  
    PD1|S|F|String^A^+1^-1^ISO^simpletext&Test&HCD^GI^simpletext&NormalString&ISO^I|NormalString^Test&Test^Test^Test^Test^Test^AE^simpletext^simpletext&Test&ISO^P^NormalString^M10^MC^simpletext&NormalString&HCD^A|N|simpletext|I|I|N|NormalString^+1^M11^simpletext&NormalString&L,M,N^RRI^simpletext&NormalString&HCD|NOVALUE^NormalString^Test^Test^NormalString^Test|N  
    PV1|1|I|2000^2012^01^JDL&test&DNS^test^test^test^test^test||||004777^DOE^JANE^A.|||SUR||||2|A0  
    ```  
  
3.  <span data-ttu-id="37db4-112">将该文件作为**BatchInBatchOut.txt**中\<*驱动器*:\>\Batching Tutorial\Instances 文件夹，然后关闭记事本。</span><span class="sxs-lookup"><span data-stu-id="37db4-112">Save the file as **BatchInBatchOut.txt** in the \<*drive*:\>\Batching Tutorial\Instances folder, and then close Notepad.</span></span>  
  
### <a name="to-create-the-create-batch-message-instance-text-files"></a><span data-ttu-id="37db4-113">若要创建的文本文件的创建批处理消息实例</span><span class="sxs-lookup"><span data-stu-id="37db4-113">To create the create batch message instance text files</span></span>  
  
1. <span data-ttu-id="37db4-114">打开记事本。</span><span class="sxs-lookup"><span data-stu-id="37db4-114">Open Notepad.</span></span>  
  
2. <span data-ttu-id="37db4-115">将以下文本复制到记事本：</span><span class="sxs-lookup"><span data-stu-id="37db4-115">Copy the following text into Notepad:</span></span>  
  
   ```  
   MSH|^~\&|Tutorial_BatchSource|XYZ_ADMITTING|Tutorial_BatchDest|XYZ_HOSPITAL|20040215115056||ADT^A03|Msg01|P|2.3.1  
   EVN|A03|199601121005||01||199601121000  
   PID|||191919^^^MYHOS^MR~123-45-6789^^^USSSA^SS|253763|SMITH^JOHN^Q||19560129|M|||123MAIN^^BUFFALO^NY^98052^""||(123)555-0100||S|M|10199925^^^MYHOS^AN|123-45-6789  
   PD1|S|F|NormalString^A^+1^-1^ISO^simpletext&Test&HCD^GI^simpletext&NormalString&ISO^I|NormalString^Test&Test^Test^Test^Test^Test^AE^simpletext^simpletext&Test&ISO^P^NormalString^M10^MC^simpletext&NormalString&HCD^A|N|simpletext|I|I|N|NormalString^+1^M11^simpletext&NormalString&L,M,N^RRI^simpletext&NormalString&HCD|NOVALUE^NormalString^Test^Test^NormalString^Test|N  
   PV1|1|I|2000^2012^01^hey&test&DNS^test^test^test^test^test||||004777^MILLER^CONNIE^A.|||SUR||||2|A0  
   ```  
  
3. <span data-ttu-id="37db4-116">将该文件作为**CreateBatchMessage1.txt**中\<*驱动器*:\>\Batching Tutorial\Instances 文件夹，然后关闭记事本。</span><span class="sxs-lookup"><span data-stu-id="37db4-116">Save the file as **CreateBatchMessage1.txt** in the \<*drive*:\>\Batching Tutorial\Instances folder, and then close Notepad.</span></span>  
  
4. <span data-ttu-id="37db4-117">将以下文本复制到记事本的新实例：</span><span class="sxs-lookup"><span data-stu-id="37db4-117">Copy the following text into a new instance of Notepad:</span></span>  
  
   ```  
   MSH|^~\&|Tutorial_BatchSource|XYZ_ADMITTING|Tutorial_BatchDest|XYZ_HOSPITAL|20040215115056||ADT^A03|Msg02|T|2.3.1  
   EVN|A03|199601121005||01||199601121000  
   PID|||191919^^^MYHOS^MR~123-45-6789^^^USSSA^SS|253763|DOE^JOHN||19560129|M|||123MAIN^^BUFFALO^NY^98052^""||(123)555-0100||S|M|10199925^^^MYHOS^AN|123-45-6789  
   PD1|S|F|String^A^+1^-1^ISO^simpletext&Test&HCD^GI^simpletext&NormalString&ISO^I|NormalString^Test&Test^Test^Test^Test^Test^AE^simpletext^simpletext&Test&ISO^P^NormalString^M10^MC^simpletext&NormalString&HCD^A|N|simpletext|I|I|N|NormalString^+1^M11^simpletext&NormalString&L,M,N^RRI^simpletext&NormalString&HCD|NOVALUE^NormalString^Test^Test^NormalString^Test|N  
   PV1|1|I|2000^2012^01^JDL&test&DNS^test^test^test^test^test||||004777^DOE^JANE^A.|||SUR||||2|A0  
   ```  
  
5. <span data-ttu-id="37db4-118">将该文件作为**CreateBatchMessage2.txt**中\<*驱动器*:\>\Batching Tutorial\Instances 文件夹，然后关闭记事本。</span><span class="sxs-lookup"><span data-stu-id="37db4-118">Save the file as **CreateBatchMessage2.txt** in the \<*drive*:\>\Batching Tutorial\Instances folder, and then close Notepad.</span></span>  
  
   <span data-ttu-id="37db4-119">请继续执行[第 1 部分：零碎的入站的批处理方案](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="37db4-119">Proceed to [Part 1: Fragmented Inbound Batch Scenario](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md).</span></span>