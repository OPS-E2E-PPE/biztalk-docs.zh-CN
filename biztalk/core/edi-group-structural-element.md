---
title: EDI 组结构元素 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 100a7118-9c02-474e-8685-9e4bb6f52e81
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c05591419e83063d8ebd8f4f79dffe801eeb2a76
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350482"
---
# <a name="edi-group-structural-element"></a><span data-ttu-id="9a4aa-102">EDI 组结构元素</span><span class="sxs-lookup"><span data-stu-id="9a4aa-102">EDI Group Structural Element</span></span>
<span data-ttu-id="9a4aa-103">组包含一个或多个事务集。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-103">The group contains one or more transaction sets.</span></span> <span data-ttu-id="9a4aa-104">一个 EDIFACT 组必须包含相同类型的事务集。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-104">An EDIFACT group must contain transaction sets of the same type.</span></span> <span data-ttu-id="9a4aa-105">X12 组可能包含类似类型的事务集 （基于事务集-组 (GS01-ST01) 映射） 或相同类型的事务集。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-105">An X12 group may contain transaction sets of similar type (based on the transaction set – group (GS01-ST01) mapping) or transaction sets of the same type.</span></span> <span data-ttu-id="9a4aa-106">下面列出了类似 X12 事务集 (ST01) 可能会一起发生在单个组 (GS01) 表。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-106">The table below lists similar X12 transaction sets (ST01), which can occur together in a single group (GS01).</span></span>  
  
|<span data-ttu-id="9a4aa-107">GS01</span><span class="sxs-lookup"><span data-stu-id="9a4aa-107">GS01</span></span>|<span data-ttu-id="9a4aa-108">ST01</span><span class="sxs-lookup"><span data-stu-id="9a4aa-108">ST01</span></span>|  
|----------|----------|  
|<span data-ttu-id="9a4aa-109">CF</span><span class="sxs-lookup"><span data-stu-id="9a4aa-109">CF</span></span>|<span data-ttu-id="9a4aa-110">844</span><span class="sxs-lookup"><span data-stu-id="9a4aa-110">844</span></span>|  
|<span data-ttu-id="9a4aa-111">CF</span><span class="sxs-lookup"><span data-stu-id="9a4aa-111">CF</span></span>|<span data-ttu-id="9a4aa-112">849</span><span class="sxs-lookup"><span data-stu-id="9a4aa-112">849</span></span>|  
|<span data-ttu-id="9a4aa-113">DX</span><span class="sxs-lookup"><span data-stu-id="9a4aa-113">DX</span></span>|<span data-ttu-id="9a4aa-114">894</span><span class="sxs-lookup"><span data-stu-id="9a4aa-114">894</span></span>|  
|<span data-ttu-id="9a4aa-115">DX</span><span class="sxs-lookup"><span data-stu-id="9a4aa-115">DX</span></span>|<span data-ttu-id="9a4aa-116">895</span><span class="sxs-lookup"><span data-stu-id="9a4aa-116">895</span></span>|  
|<span data-ttu-id="9a4aa-117">FR</span><span class="sxs-lookup"><span data-stu-id="9a4aa-117">FR</span></span>|<span data-ttu-id="9a4aa-118">821</span><span class="sxs-lookup"><span data-stu-id="9a4aa-118">821</span></span>|  
|<span data-ttu-id="9a4aa-119">FR</span><span class="sxs-lookup"><span data-stu-id="9a4aa-119">FR</span></span>|<span data-ttu-id="9a4aa-120">827</span><span class="sxs-lookup"><span data-stu-id="9a4aa-120">827</span></span>|  
|<span data-ttu-id="9a4aa-121">GC</span><span class="sxs-lookup"><span data-stu-id="9a4aa-121">GC</span></span>|<span data-ttu-id="9a4aa-122">920</span><span class="sxs-lookup"><span data-stu-id="9a4aa-122">920</span></span>|  
|<span data-ttu-id="9a4aa-123">GC</span><span class="sxs-lookup"><span data-stu-id="9a4aa-123">GC</span></span>|<span data-ttu-id="9a4aa-124">924</span><span class="sxs-lookup"><span data-stu-id="9a4aa-124">924</span></span>|  
|<span data-ttu-id="9a4aa-125">GC</span><span class="sxs-lookup"><span data-stu-id="9a4aa-125">GC</span></span>|<span data-ttu-id="9a4aa-126">925</span><span class="sxs-lookup"><span data-stu-id="9a4aa-126">925</span></span>|  
|<span data-ttu-id="9a4aa-127">GC</span><span class="sxs-lookup"><span data-stu-id="9a4aa-127">GC</span></span>|<span data-ttu-id="9a4aa-128">926</span><span class="sxs-lookup"><span data-stu-id="9a4aa-128">926</span></span>|  
|<span data-ttu-id="9a4aa-129">HC</span><span class="sxs-lookup"><span data-stu-id="9a4aa-129">HC</span></span>|<span data-ttu-id="9a4aa-130">837</span><span class="sxs-lookup"><span data-stu-id="9a4aa-130">837</span></span>|  
|<span data-ttu-id="9a4aa-131">HC</span><span class="sxs-lookup"><span data-stu-id="9a4aa-131">HC</span></span>|<span data-ttu-id="9a4aa-132">837_D</span><span class="sxs-lookup"><span data-stu-id="9a4aa-132">837_D</span></span>|  
|<span data-ttu-id="9a4aa-133">HC</span><span class="sxs-lookup"><span data-stu-id="9a4aa-133">HC</span></span>|<span data-ttu-id="9a4aa-134">837_I</span><span class="sxs-lookup"><span data-stu-id="9a4aa-134">837_I</span></span>|  
|<span data-ttu-id="9a4aa-135">HC</span><span class="sxs-lookup"><span data-stu-id="9a4aa-135">HC</span></span>|<span data-ttu-id="9a4aa-136">837_P</span><span class="sxs-lookup"><span data-stu-id="9a4aa-136">837_P</span></span>|  
|<span data-ttu-id="9a4aa-137">IA</span><span class="sxs-lookup"><span data-stu-id="9a4aa-137">IA</span></span>|<span data-ttu-id="9a4aa-138">110</span><span class="sxs-lookup"><span data-stu-id="9a4aa-138">110</span></span>|  
|<span data-ttu-id="9a4aa-139">IA</span><span class="sxs-lookup"><span data-stu-id="9a4aa-139">IA</span></span>|<span data-ttu-id="9a4aa-140">980</span><span class="sxs-lookup"><span data-stu-id="9a4aa-140">980</span></span>|  
|<span data-ttu-id="9a4aa-141">IO</span><span class="sxs-lookup"><span data-stu-id="9a4aa-141">IO</span></span>|<span data-ttu-id="9a4aa-142">310</span><span class="sxs-lookup"><span data-stu-id="9a4aa-142">310</span></span>|  
|<span data-ttu-id="9a4aa-143">IO</span><span class="sxs-lookup"><span data-stu-id="9a4aa-143">IO</span></span>|<span data-ttu-id="9a4aa-144">312</span><span class="sxs-lookup"><span data-stu-id="9a4aa-144">312</span></span>|  
|<span data-ttu-id="9a4aa-145">ME</span><span class="sxs-lookup"><span data-stu-id="9a4aa-145">ME</span></span>|<span data-ttu-id="9a4aa-146">198</span><span class="sxs-lookup"><span data-stu-id="9a4aa-146">198</span></span>|  
|<span data-ttu-id="9a4aa-147">ME</span><span class="sxs-lookup"><span data-stu-id="9a4aa-147">ME</span></span>|<span data-ttu-id="9a4aa-148">200</span><span class="sxs-lookup"><span data-stu-id="9a4aa-148">200</span></span>|  
|<span data-ttu-id="9a4aa-149">ME</span><span class="sxs-lookup"><span data-stu-id="9a4aa-149">ME</span></span>|<span data-ttu-id="9a4aa-150">201</span><span class="sxs-lookup"><span data-stu-id="9a4aa-150">201</span></span>|  
|<span data-ttu-id="9a4aa-151">ME</span><span class="sxs-lookup"><span data-stu-id="9a4aa-151">ME</span></span>|<span data-ttu-id="9a4aa-152">245</span><span class="sxs-lookup"><span data-stu-id="9a4aa-152">245</span></span>|  
|<span data-ttu-id="9a4aa-153">ME</span><span class="sxs-lookup"><span data-stu-id="9a4aa-153">ME</span></span>|<span data-ttu-id="9a4aa-154">261</span><span class="sxs-lookup"><span data-stu-id="9a4aa-154">261</span></span>|  
|<span data-ttu-id="9a4aa-155">ME</span><span class="sxs-lookup"><span data-stu-id="9a4aa-155">ME</span></span>|<span data-ttu-id="9a4aa-156">262</span><span class="sxs-lookup"><span data-stu-id="9a4aa-156">262</span></span>|  
|<span data-ttu-id="9a4aa-157">ME</span><span class="sxs-lookup"><span data-stu-id="9a4aa-157">ME</span></span>|<span data-ttu-id="9a4aa-158">263</span><span class="sxs-lookup"><span data-stu-id="9a4aa-158">263</span></span>|  
|<span data-ttu-id="9a4aa-159">ME</span><span class="sxs-lookup"><span data-stu-id="9a4aa-159">ME</span></span>|<span data-ttu-id="9a4aa-160">833</span><span class="sxs-lookup"><span data-stu-id="9a4aa-160">833</span></span>|  
|<span data-ttu-id="9a4aa-161">ME</span><span class="sxs-lookup"><span data-stu-id="9a4aa-161">ME</span></span>|<span data-ttu-id="9a4aa-162">872</span><span class="sxs-lookup"><span data-stu-id="9a4aa-162">872</span></span>|  
|<span data-ttu-id="9a4aa-163">MG</span><span class="sxs-lookup"><span data-stu-id="9a4aa-163">MG</span></span>|<span data-ttu-id="9a4aa-164">203</span><span class="sxs-lookup"><span data-stu-id="9a4aa-164">203</span></span>|  
|<span data-ttu-id="9a4aa-165">MG</span><span class="sxs-lookup"><span data-stu-id="9a4aa-165">MG</span></span>|<span data-ttu-id="9a4aa-166">206</span><span class="sxs-lookup"><span data-stu-id="9a4aa-166">206</span></span>|  
|<span data-ttu-id="9a4aa-167">MG</span><span class="sxs-lookup"><span data-stu-id="9a4aa-167">MG</span></span>|<span data-ttu-id="9a4aa-168">259</span><span class="sxs-lookup"><span data-stu-id="9a4aa-168">259</span></span>|  
|<span data-ttu-id="9a4aa-169">MG</span><span class="sxs-lookup"><span data-stu-id="9a4aa-169">MG</span></span>|<span data-ttu-id="9a4aa-170">260</span><span class="sxs-lookup"><span data-stu-id="9a4aa-170">260</span></span>|  
|<span data-ttu-id="9a4aa-171">MG</span><span class="sxs-lookup"><span data-stu-id="9a4aa-171">MG</span></span>|<span data-ttu-id="9a4aa-172">264</span><span class="sxs-lookup"><span data-stu-id="9a4aa-172">264</span></span>|  
|<span data-ttu-id="9a4aa-173">MG</span><span class="sxs-lookup"><span data-stu-id="9a4aa-173">MG</span></span>|<span data-ttu-id="9a4aa-174">266</span><span class="sxs-lookup"><span data-stu-id="9a4aa-174">266</span></span>|  
|<span data-ttu-id="9a4aa-175">OG</span><span class="sxs-lookup"><span data-stu-id="9a4aa-175">OG</span></span>|<span data-ttu-id="9a4aa-176">875</span><span class="sxs-lookup"><span data-stu-id="9a4aa-176">875</span></span>|  
|<span data-ttu-id="9a4aa-177">OG</span><span class="sxs-lookup"><span data-stu-id="9a4aa-177">OG</span></span>|<span data-ttu-id="9a4aa-178">876</span><span class="sxs-lookup"><span data-stu-id="9a4aa-178">876</span></span>|  
|<span data-ttu-id="9a4aa-179">PK</span><span class="sxs-lookup"><span data-stu-id="9a4aa-179">PK</span></span>|<span data-ttu-id="9a4aa-180">196</span><span class="sxs-lookup"><span data-stu-id="9a4aa-180">196</span></span>|  
|<span data-ttu-id="9a4aa-181">PK</span><span class="sxs-lookup"><span data-stu-id="9a4aa-181">PK</span></span>|<span data-ttu-id="9a4aa-182">839</span><span class="sxs-lookup"><span data-stu-id="9a4aa-182">839</span></span>|  
|<span data-ttu-id="9a4aa-183">QG</span><span class="sxs-lookup"><span data-stu-id="9a4aa-183">QG</span></span>|<span data-ttu-id="9a4aa-184">878</span><span class="sxs-lookup"><span data-stu-id="9a4aa-184">878</span></span>|  
|<span data-ttu-id="9a4aa-185">QG</span><span class="sxs-lookup"><span data-stu-id="9a4aa-185">QG</span></span>|<span data-ttu-id="9a4aa-186">879</span><span class="sxs-lookup"><span data-stu-id="9a4aa-186">879</span></span>|  
|<span data-ttu-id="9a4aa-187">QG</span><span class="sxs-lookup"><span data-stu-id="9a4aa-187">QG</span></span>|<span data-ttu-id="9a4aa-188">888</span><span class="sxs-lookup"><span data-stu-id="9a4aa-188">888</span></span>|  
|<span data-ttu-id="9a4aa-189">QG</span><span class="sxs-lookup"><span data-stu-id="9a4aa-189">QG</span></span>|<span data-ttu-id="9a4aa-190">889</span><span class="sxs-lookup"><span data-stu-id="9a4aa-190">889</span></span>|  
|<span data-ttu-id="9a4aa-191">QG</span><span class="sxs-lookup"><span data-stu-id="9a4aa-191">QG</span></span>|<span data-ttu-id="9a4aa-192">896</span><span class="sxs-lookup"><span data-stu-id="9a4aa-192">896</span></span>|  
|<span data-ttu-id="9a4aa-193">QO</span><span class="sxs-lookup"><span data-stu-id="9a4aa-193">QO</span></span>|<span data-ttu-id="9a4aa-194">313</span><span class="sxs-lookup"><span data-stu-id="9a4aa-194">313</span></span>|  
|<span data-ttu-id="9a4aa-195">QO</span><span class="sxs-lookup"><span data-stu-id="9a4aa-195">QO</span></span>|<span data-ttu-id="9a4aa-196">315</span><span class="sxs-lookup"><span data-stu-id="9a4aa-196">315</span></span>|  
|<span data-ttu-id="9a4aa-197">RO</span><span class="sxs-lookup"><span data-stu-id="9a4aa-197">RO</span></span>|<span data-ttu-id="9a4aa-198">300</span><span class="sxs-lookup"><span data-stu-id="9a4aa-198">300</span></span>|  
|<span data-ttu-id="9a4aa-199">RO</span><span class="sxs-lookup"><span data-stu-id="9a4aa-199">RO</span></span>|<span data-ttu-id="9a4aa-200">301</span><span class="sxs-lookup"><span data-stu-id="9a4aa-200">301</span></span>|  
|<span data-ttu-id="9a4aa-201">RO</span><span class="sxs-lookup"><span data-stu-id="9a4aa-201">RO</span></span>|<span data-ttu-id="9a4aa-202">303</span><span class="sxs-lookup"><span data-stu-id="9a4aa-202">303</span></span>|  
|<span data-ttu-id="9a4aa-203">RQ</span><span class="sxs-lookup"><span data-stu-id="9a4aa-203">RQ</span></span>|<span data-ttu-id="9a4aa-204">836</span><span class="sxs-lookup"><span data-stu-id="9a4aa-204">836</span></span>|  
|<span data-ttu-id="9a4aa-205">RQ</span><span class="sxs-lookup"><span data-stu-id="9a4aa-205">RQ</span></span>|<span data-ttu-id="9a4aa-206">840</span><span class="sxs-lookup"><span data-stu-id="9a4aa-206">840</span></span>|  
|<span data-ttu-id="9a4aa-207">RS</span><span class="sxs-lookup"><span data-stu-id="9a4aa-207">RS</span></span>|<span data-ttu-id="9a4aa-208">869</span><span class="sxs-lookup"><span data-stu-id="9a4aa-208">869</span></span>|  
|<span data-ttu-id="9a4aa-209">RS</span><span class="sxs-lookup"><span data-stu-id="9a4aa-209">RS</span></span>|<span data-ttu-id="9a4aa-210">870</span><span class="sxs-lookup"><span data-stu-id="9a4aa-210">870</span></span>|  
|<span data-ttu-id="9a4aa-211">SL</span><span class="sxs-lookup"><span data-stu-id="9a4aa-211">SL</span></span>|<span data-ttu-id="9a4aa-212">135</span><span class="sxs-lookup"><span data-stu-id="9a4aa-212">135</span></span>|  
|<span data-ttu-id="9a4aa-213">SL</span><span class="sxs-lookup"><span data-stu-id="9a4aa-213">SL</span></span>|<span data-ttu-id="9a4aa-214">139</span><span class="sxs-lookup"><span data-stu-id="9a4aa-214">139</span></span>|  
|<span data-ttu-id="9a4aa-215">SO</span><span class="sxs-lookup"><span data-stu-id="9a4aa-215">SO</span></span>|<span data-ttu-id="9a4aa-216">302</span><span class="sxs-lookup"><span data-stu-id="9a4aa-216">302</span></span>|  
|<span data-ttu-id="9a4aa-217">SO</span><span class="sxs-lookup"><span data-stu-id="9a4aa-217">SO</span></span>|<span data-ttu-id="9a4aa-218">311</span><span class="sxs-lookup"><span data-stu-id="9a4aa-218">311</span></span>|  
|<span data-ttu-id="9a4aa-219">SO</span><span class="sxs-lookup"><span data-stu-id="9a4aa-219">SO</span></span>|<span data-ttu-id="9a4aa-220">317</span><span class="sxs-lookup"><span data-stu-id="9a4aa-220">317</span></span>|  
|<span data-ttu-id="9a4aa-221">SO</span><span class="sxs-lookup"><span data-stu-id="9a4aa-221">SO</span></span>|<span data-ttu-id="9a4aa-222">319</span><span class="sxs-lookup"><span data-stu-id="9a4aa-222">319</span></span>|  
|<span data-ttu-id="9a4aa-223">SO</span><span class="sxs-lookup"><span data-stu-id="9a4aa-223">SO</span></span>|<span data-ttu-id="9a4aa-224">322</span><span class="sxs-lookup"><span data-stu-id="9a4aa-224">322</span></span>|  
|<span data-ttu-id="9a4aa-225">SO</span><span class="sxs-lookup"><span data-stu-id="9a4aa-225">SO</span></span>|<span data-ttu-id="9a4aa-226">323</span><span class="sxs-lookup"><span data-stu-id="9a4aa-226">323</span></span>|  
|<span data-ttu-id="9a4aa-227">SO</span><span class="sxs-lookup"><span data-stu-id="9a4aa-227">SO</span></span>|<span data-ttu-id="9a4aa-228">324</span><span class="sxs-lookup"><span data-stu-id="9a4aa-228">324</span></span>|  
|<span data-ttu-id="9a4aa-229">SO</span><span class="sxs-lookup"><span data-stu-id="9a4aa-229">SO</span></span>|<span data-ttu-id="9a4aa-230">325</span><span class="sxs-lookup"><span data-stu-id="9a4aa-230">325</span></span>|  
|<span data-ttu-id="9a4aa-231">SO</span><span class="sxs-lookup"><span data-stu-id="9a4aa-231">SO</span></span>|<span data-ttu-id="9a4aa-232">326</span><span class="sxs-lookup"><span data-stu-id="9a4aa-232">326</span></span>|  
|<span data-ttu-id="9a4aa-233">SO</span><span class="sxs-lookup"><span data-stu-id="9a4aa-233">SO</span></span>|<span data-ttu-id="9a4aa-234">361</span><span class="sxs-lookup"><span data-stu-id="9a4aa-234">361</span></span>|  
|<span data-ttu-id="9a4aa-235">TO</span><span class="sxs-lookup"><span data-stu-id="9a4aa-235">TO</span></span>|<span data-ttu-id="9a4aa-236">197</span><span class="sxs-lookup"><span data-stu-id="9a4aa-236">197</span></span>|  
|<span data-ttu-id="9a4aa-237">TO</span><span class="sxs-lookup"><span data-stu-id="9a4aa-237">TO</span></span>|<span data-ttu-id="9a4aa-238">199</span><span class="sxs-lookup"><span data-stu-id="9a4aa-238">199</span></span>|  
|<span data-ttu-id="9a4aa-239">TO</span><span class="sxs-lookup"><span data-stu-id="9a4aa-239">TO</span></span>|<span data-ttu-id="9a4aa-240">265</span><span class="sxs-lookup"><span data-stu-id="9a4aa-240">265</span></span>|  
|<span data-ttu-id="9a4aa-241">TO</span><span class="sxs-lookup"><span data-stu-id="9a4aa-241">TO</span></span>|<span data-ttu-id="9a4aa-242">485</span><span class="sxs-lookup"><span data-stu-id="9a4aa-242">485</span></span>|  
|<span data-ttu-id="9a4aa-243">TO</span><span class="sxs-lookup"><span data-stu-id="9a4aa-243">TO</span></span>|<span data-ttu-id="9a4aa-244">486</span><span class="sxs-lookup"><span data-stu-id="9a4aa-244">486</span></span>|  
|<span data-ttu-id="9a4aa-245">TP</span><span class="sxs-lookup"><span data-stu-id="9a4aa-245">TP</span></span>|<span data-ttu-id="9a4aa-246">460</span><span class="sxs-lookup"><span data-stu-id="9a4aa-246">460</span></span>|  
|<span data-ttu-id="9a4aa-247">TP</span><span class="sxs-lookup"><span data-stu-id="9a4aa-247">TP</span></span>|<span data-ttu-id="9a4aa-248">463</span><span class="sxs-lookup"><span data-stu-id="9a4aa-248">463</span></span>|  
|<span data-ttu-id="9a4aa-249">TP</span><span class="sxs-lookup"><span data-stu-id="9a4aa-249">TP</span></span>|<span data-ttu-id="9a4aa-250">466</span><span class="sxs-lookup"><span data-stu-id="9a4aa-250">466</span></span>|  
|<span data-ttu-id="9a4aa-251">TP</span><span class="sxs-lookup"><span data-stu-id="9a4aa-251">TP</span></span>|<span data-ttu-id="9a4aa-252">468</span><span class="sxs-lookup"><span data-stu-id="9a4aa-252">468</span></span>|  
|<span data-ttu-id="9a4aa-253">TP</span><span class="sxs-lookup"><span data-stu-id="9a4aa-253">TP</span></span>|<span data-ttu-id="9a4aa-254">490</span><span class="sxs-lookup"><span data-stu-id="9a4aa-254">490</span></span>|  
|<span data-ttu-id="9a4aa-255">TP</span><span class="sxs-lookup"><span data-stu-id="9a4aa-255">TP</span></span>|<span data-ttu-id="9a4aa-256">492</span><span class="sxs-lookup"><span data-stu-id="9a4aa-256">492</span></span>|  
|<span data-ttu-id="9a4aa-257">TP</span><span class="sxs-lookup"><span data-stu-id="9a4aa-257">TP</span></span>|<span data-ttu-id="9a4aa-258">494</span><span class="sxs-lookup"><span data-stu-id="9a4aa-258">494</span></span>|  
|<span data-ttu-id="9a4aa-259">WA</span><span class="sxs-lookup"><span data-stu-id="9a4aa-259">WA</span></span>|<span data-ttu-id="9a4aa-260">140</span><span class="sxs-lookup"><span data-stu-id="9a4aa-260">140</span></span>|  
|<span data-ttu-id="9a4aa-261">WA</span><span class="sxs-lookup"><span data-stu-id="9a4aa-261">WA</span></span>|<span data-ttu-id="9a4aa-262">141</span><span class="sxs-lookup"><span data-stu-id="9a4aa-262">141</span></span>|  
|<span data-ttu-id="9a4aa-263">WA</span><span class="sxs-lookup"><span data-stu-id="9a4aa-263">WA</span></span>|<span data-ttu-id="9a4aa-264">142</span><span class="sxs-lookup"><span data-stu-id="9a4aa-264">142</span></span>|  
|<span data-ttu-id="9a4aa-265">WA</span><span class="sxs-lookup"><span data-stu-id="9a4aa-265">WA</span></span>|<span data-ttu-id="9a4aa-266">143</span><span class="sxs-lookup"><span data-stu-id="9a4aa-266">143</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="9a4aa-267">HIPAA 5010 组还允许单个组中的不同版本的事务集。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-267">A HIPAA 5010 group also allows transaction sets of different versions within a single group.</span></span>  
  
 <span data-ttu-id="9a4aa-268">如果处理事务集时遇到异常，则挂起 EDI 参与方属性用于确定是否设置整个交换还是仅失败的事务。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-268">If an exception is encountered when processing a transaction set, EDI party properties are used to determine if the entire interchange or only the failing transaction set is suspended.</span></span>  
  
 <span data-ttu-id="9a4aa-269">组必须使用功能组标头 (GS 在 X12 中) 或在 EDIFACT 中，UNG 开头，它必须以功能组尾部 (X12 中的 GE) 或 EDIFACT 中的 UNE 结尾。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-269">A group must start with a Functional Group Header (GS in X12 or UNG in EDIFACT), and it must end with a Functional Group Trailer (GE in X12 or UNE in EDIFACT).</span></span> <span data-ttu-id="9a4aa-270">组标头包含发送方和接收方代码、 日期和时间、 与标头和尾部，定义可能会包含在功能组和其他信息的事务集的集合的组标识符相匹配的控制编号。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-270">The Group Header contains sender and receiver codes, a date and time, a control number that matches the header and trailer, a group identifier that defines the collection of transaction sets that may be included within the functional group, and other information.</span></span> <span data-ttu-id="9a4aa-271">组尾部具有指示组内事务集数目的元素。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-271">The Group Trailer has an element that indicates the number of transaction sets within the group.</span></span>  
  
 <span data-ttu-id="9a4aa-272">组是可选的 EDIFACT 交换中。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-272">A group is optional in an EDIFACT interchange.</span></span> <span data-ttu-id="9a4aa-273">EDIFACT 交换可以包含多个事务集，即使不不存在任何组 （UNG 段不存在）。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-273">An EDIFACT interchange can contain multiple transaction sets even if no group is present (the UNG segment is not present).</span></span> <span data-ttu-id="9a4aa-274">在这种情况下，的事务集必须均为相同的类型，如单个组中的事务集必须属于同一类型。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-274">In this case, the transaction sets must all be of the same type, as transaction sets in a single group must be of the same type.</span></span> <span data-ttu-id="9a4aa-275">例如，APERAK 和 ORDERS 事务集可能不能同时是存在于单个组或不具有多个组的交换中。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-275">For example, APERAK and ORDERS transaction sets could not both be present in a single group or in an interchange that does not have multiple groups.</span></span>  
  
 <span data-ttu-id="9a4aa-276">一组需要在 X12 交换。</span><span class="sxs-lookup"><span data-stu-id="9a4aa-276">A group is required in an X12 interchange.</span></span>