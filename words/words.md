<div class="section">
    <div>
    	<iframe id="splash" width="960" height="480" src="banners/splash.html"></iframe>
        <div style="top: 70px;font-size: 75px;font-weight: bold;">
        	接下來會發生什麼事？
       	</div>
		<div style="font-weight: 500;top: 140px;left: 10px;font-size: 29px;">
			用互動式模擬解釋 COVID-19 疫情的可能發展
		</div>
		<div style="font-weight: 100;top: 189px;left: 10px;font-size: 19px;line-height: 21px;">
			<b>
				🕐 遊玩／閱讀時間：30分鐘
				&nbsp;&middot;&nbsp;
			</b>
			作者：
			<a href="https://scholar.google.com/citations?user=_wHMGkUAAAAJ&amp;hl=en">Marcel Salathé</a>
			(流行病學家)            
			&
			<a href="https://ncase.me/">Nicky Case</a>
			（美術／程式）
		</div>
	</div>
</div>

「唯一需要恐懼的是恐懼本身」是個愚蠢的建議。

Sure, don't hoard toilet paper – but if policymakers fear fear itself, they'll downplay real dangers to avoid "mass panic". Fear's not the problem, it's how we *channel* our fear. Fear gives us energy to deal with dangers now, and prepare for dangers later.

當然不用去囤購衛生紙，但如果政策制定者害怕恐懼的話，他們就會降低真實的危險來避免「集體恐慌」。恐懼本身不是問題，問題是我們如何轉化我們的恐懼，恐懼給我們對付當下危險的力量，並且為未來的危機做準備。

Honestly, we (Marcel, epidemiologist + Nicky, art/code) are worried. We bet you are, too! That's why we've channelled our fear into making these **playable simulations**, so that *you* can channel your fear into understanding:

老實說我們（流行病學家 Marcel＋Nicky 美術／程式）很擔心，我們猜你也是！這是為什麼我們將恐懼化為製作這些可互動模擬的動力，讓你們可以將恐懼化為瞭解。

* **接下來的幾週**（流行病學 101、SEIR 模型、R & R<sub>0</sub>）
* **接下來的幾個月**（封鎖、疫情調查(contact tracing?)、口罩）
* **接下來的數年**（失去免疫力？沒有疫苗？）

This guide (published May 1st, 2020. click this footnote!→[^timestamp]) is meant to give you hope *and* fear. To beat COVID-19 **in a way that also protects our mental & financial health**, we need optimism to create plans, and pessimism to create backup plans. As Gladys Bronwyn Stern once said, *“The optimist invents the airplane and the pessimist the parachute.”*

這份指南（2020年5月1日出版，點擊註腳！→[^timestamp]）的主旨是要給你盼望和恐懼。為了以**確保我們心理健康及財政健全**的方式打敗新冠病毒，我們需要樂觀地制定計劃，並且悲觀地制定備案。正如 Gladys Brownwyn Stern 曾說過的：「樂觀者發明飛機而悲觀者發明降落傘。」

[^timestamp]: These footnotes will have sources, links, or bonus commentary. Like this commentary! 註腳將包含來源、連結或額外的註解，如同這個註解！
    
    **This guide was published on May 1st, 2020.** Many details will become outdated, but we're confident this guide will cover 95% of possible futures, and that Epidemiology 101 will remain forever useful. **這份指南的出版時間為2020年5月1日**，許多細節將會變得過時，但我們有信心這份指南將包含95%的可能未來，而流行病學101將會永遠有用。

So, buckle in: we're about to experience some turbulence.

所以請繫好安全帶，我們將遭遇亂流。

<div class="section chapter">
    <div>
		<img src="banners/curve.png" height=480 style="position: absolute;"/>
        <div>之前的幾個月</div>
    </div>
</div>

Pilots use flight simulators to learn how not to crash planes.

飛行員用飛行模擬器來避免如何避免飛機失事。

**Epidemiologists use epidemic simulators to learn how not to crash humanity.**

**流行病學家使用傳染病模擬器來避免人類滅亡。**

So, let's make a very, *very* simple "epidemic flight simulator"! In this simulation, <icon i></icon> Infectious people can turn <icon s></icon> Susceptible people into more <icon i></icon> Infectious people:

所以讓我們來做一個非常、*非常*簡單的「傳染病模擬器」！在這個模擬中 <icon i></icon> 感染者 <icon s></icon> 可以將疾病傳播給易感者，因而產生更多 <icon i></icon> 感染者:

![](pics/spread.png)

It's estimated that, *at the start* of a COVID-19 outbreak, the virus jumps from an <icon i></icon> to an <icon s></icon> every 4 days, *on average*.[^_interval] (remember, there's a lot of variation)

經過估計，在 COVID-19 爆發初期，*平均*每四天病毒從一個 <icon i></icon> 傳播到一個 <icon s></icon> [^serial_interval] (記住這有很多變因)


[^serial_interval]: “The mean [serial] interval was 3.96 days (95% CI 3.53–4.39 days)”. [Du Z, Xu X, Wu Y, Wang L, Cowling BJ, Ancel Meyers L](https://wwwnc.cdc.gov/eid/article/26/6/20-0357_article) (Disclaimer: Early release articles are not considered as final versions) 「平均世代間隔為3.96天（95%信賴區間為3.53-4.39天）」[Du Z, Xu X, Wu Y, Wang L, Cowling BJ, Ancel Meyers L]https://wwwnc.cdc.gov/eid/article/26/6/20-0357_article)（聲明：早期發布文章並不被視為最終版）

If we simulate "double every 4 days" *and nothing else*, on a population starting with just 0.001% <span class="nowrap"><icon i></icon>,</span> what happens? 

如果我們*只用*「每四天感染者增加一倍」這個條件在只有 0.001% 感染者的初始條件下<span class="nowrap"><icon i></icon>，</span>會發生什麼事？

**Click "Start" to play the simulation! You can re-play it later with different settings:** (technical caveats: [^caveats])

**點擊「開始」來遊玩！你可以在之後以不同的條件再玩一次：** （技術警告：[^caveats]）

[^caveats]: **Remember: all these simulations are super simplified, for educational purposes.** **記住：所有的模擬都為了教育目的過度簡化**
    
    One simplification: When you tell this simulation "Infect 1 new person every X days", it's actually increasing # of infected by 1/X each day. Same for future settings in these simulations – "Recover every X days" is actually reducing # of infected by 1/X each day.
    其中一個簡化：當你叫這個模擬器「每X天感染1人」，它實際上做的是每天增加1/X個感染者。所以接下來的模擬都是依照這個設定。「每X天復原」的意思是每天減少1/X個感染者。
    Those *aren't* exactly the same, but it's close enough, and for educational purposes it's less opaque than setting the transmission/recovery rates directly.
    它們的意思*並不*完全一樣但已足夠接近，而且比起直接設定傳染率／復原率這比較容易理解並符合教育的宗旨。

<div class="sim">
		<iframe src="sim?stage=epi-1" width="800" height="540"></iframe>
</div>

This is the **exponential growth curve.** Starts small, then explodes. "Oh it's just a flu" to "Oh right, flus don't create *mass graves in rich cities*". 

這是一條**指數增長的曲線**。一開始很小、然後爆炸。從「喔這只是流感」到「好啦！流感不會讓富裕的城市出現萬人塚。」

![](pics/exponential.png)

But, this simulation is wrong. Exponential growth, thankfully, can't go on forever. One thing that stops a virus from spreading is if others *already* have the virus:

但這個模擬是錯的。幸好指數增長不能永遠持續。其中一件阻止病毒傳播的因素是其他人是否*已經*得到這個病毒。

![](pics/susceptibles.png)

The more <span class="nowrap"><icon i></icon>s</span> there are, the faster <span class="nowrap"><icon s></icon>s</span> become <span class="nowrap"><icon i></icon>s,</span> **but the fewer <span class="nowrap"><icon s></icon>s</span> there are, the *slower* <span class="nowrap"><icon s></icon>s</span> become <span class="nowrap"><icon i></icon>s.</span>**

越多 <span class="nowrap"><icon i></icon></span> 的時候, <span class="nowrap"><icon s></icon>s</span> 越快變成 <span class="nowrap"><icon i></icon>，</span> **但 <span class="nowrap"><icon s></icon>越少的時候</span>，<span class="nowrap"><icon s></icon>s</span> *越慢*變成 <span class="nowrap"><icon i></icon>.</span>**

How's this change the growth of an epidemic? Let's find out:

這如何改變疫情的增長呢？讓我們試試看：

<div class="sim">
		<iframe src="sim?stage=epi-2" width="800" height="540"></iframe>
</div>

This is the "S-shaped" **logistic growth curve.** Starts small, explodes, then slows down again.

這是一條「S型」的**邏輯增長曲線（logistic growth curve）**，一開始很小、爆炸性增長、然後增長重新慢下來。

But, this simulation is *still* wrong. We're missing the fact that <icon i></icon> Infectious people eventually stop being infectious, either by 1) recovering, 2) "recovering" with lung damage, or 3) dying.

但這個模擬*依然*不對，我們忽略患者最後將不再具有感染性，不管是因為患者 1) 復原 2) 帶著肺損傷的「復原」 3) 死亡。

For simplicity's sake, let's pretend that all <icon i></icon> Infectious people become <icon r></icon> Recovered. (Just remember that in reality, some are dead.) <span class="nowrap"><icon r></icon>s</span> can't be infected again, and let's pretend – *for now!* – that they stay immune for life.

為了簡化問題，我們假設所有的<icon i></icon>患者都將<icon r></icon>復原（只要記得在現實中有些人過世了）。<span class="nowrap"><icon r></icon></span>不再具有感染性，並且讓我們假設—只有現在！—他們終身免疫。

With COVID-19, it's estimated you're <icon i></icon> Infectious for 10 days, *on average*.[^infectiousness] That means some folks will recover before 10 days, some after. **Here's what that looks like, with a simulation *starting* with 100% <span class="nowrap"><icon i></icon>:</span>**

根據估計，如果你得到 COVID-19，平均來說你有10天具有傳染性。[^infectiousness]這意味著有些人在10天內復原，有些人需要更長的時間。**這是初始條件為 100% <span class="nowrap"><icon i></icon>長的樣子：</span>**

[^infectiousness]: “The median communicable period \[...\] was 9.5 days.” [Hu, Z., Song, C., Xu, C. et al](https://link.springer.com/article/10.1007/s11427-020-1661-4) Yes, we know "median" is not the same as "average". For simplified educational purposes, close enough. 「可傳播病毒的中位數為9.5天」[Hu, Z., Song, C., Xu, C. et al](https://link.springer.com/article/10.1007/s11427-020-1661-4) 我們都知道「中位數」不等於「平均數」，但對於教育目的來說已經足夠接近了。

<div class="sim">
		<iframe src="sim?stage=epi-3" width="800" height="540"></iframe>
</div>

This is the opposite of exponential growth, the **exponential decay curve.**

這是指數增長的相反，「指數遞減曲線」。

Now, what happens if you simulate S-shaped logistic growth *with* recovery?

那如果我們把「復原」這個條件加入S型邏輯增長的模擬中，會發生什麼事呢？

![](pics/graphs_q.png)

Let's find out.

讓我們來試試看。

<b style='color:#ff4040'>紅色曲線</b> 是*現存*病例 <span class="nowrap"><icon i></icon>,</span>    
<b style='color:#999999'>灰色曲線</b> 是病例*總數*（現存＋治癒<span class="nowrap"><icon r></icon>），</span>
開始只有0.001% <span class="nowrap"><icon i></icon>:</span>

<div class="sim">
		<iframe src="sim?stage=epi-4" width="800" height="540"></iframe>
</div>

And *that's* where that famous curve comes from! It's not a bell curve, it's not even a "log-normal" curve. It has no name. But you've seen it a zillion times, and beseeched to flatten.

這*正是*那條有名曲線的由來！它不是鐘形曲線，它甚至不是一條「對數—常態分佈」曲線，它沒有名字，但你見過它無數遍，而且希望它扁下來。

這是 **SIR 模型**,[^sir]    
(<icon s></icon>**S**usceptible <icon i></icon>**I**nfectious <icon r></icon>**R**ecovered)      
流行病學導論裡*第二重要*的概念：

[^sir]: 想要SIR模型更詳細的描述，請參考 [the Institute for Disease Modeling](https://www.idmod.org/docs/hiv/model-sir.html#) 和 [Wikipedia](https://en.wikipedia.org/wiki/Compartmental_models_in_epidemiology#The_SIR_model)

![](pics/sir.png)

**NOTE: The simulations that inform policy are way, *way* more sophisticated than this!** But the SIR Model can still explain the same general findings, even if missing the nuances.

**註：政策制定所需的模擬比這個*複雜得多*了！** 但SIR模型在大方向上仍是正確的，即使少了一些細節。

Actually, let's add one more nuance: before an <icon s></icon> becomes an <span class="nowrap"><icon i></icon>,</span> they first become <icon e></icon> Exposed. This is when they have the virus but can't pass it on yet – infect*ed* but not yet infect*ious*.

讓我們再加入一個小細節：在 <icon s></icon> 變成 <span class="nowrap"><icon i></icon>,</span> 之前，他會先變成<icon e></icon>潛伏者。

![](pics/seir.png)

(This variant is called the **SEIR Model**[^seir], where the "E" stands for <icon e></icon> "Exposed". Note this *isn't* the everyday meaning of "exposed", when you may or may not have the virus. In this technical definition, "Exposed" means you definitely have it. Science terminology is bad.)

（這個變體叫做 **SEIR 模型**[^seir]，其中「E」代表「潛伏（Exposed）」<icon e></icon>。請注意這跟日常生活中「暴露於（  Exposed）」（不管你有沒有得到病毒）的意思*並不一樣*。在這裡，「潛伏」的意思是你一定得到它了。科學用語很爛。）

[^seir]: For more technical explanations of the SEIR Model, see [the Institute for Disease Modeling](https://www.idmod.org/docs/hiv/model-seir.html) and [Wikipedia](https://en.wikipedia.org/wiki/Compartmental_models_in_epidemiology#The_SEIR_model) 對於SEIR更詳細的描述，參見 [the Institute for Disease Modeling](https://www.idmod.org/docs/hiv/model-seir.html) 和 [Wikipedia](https://en.wikipedia.org/wiki/Compartmental_models_in_epidemiology#The_SEIR_model)

For COVID-19, it's estimated that you're <icon e></icon> infected-but-not-yet-infectious for 3 days, *on average*.[^latent] What happens if we add that to the simulation?

根據估計，對於COVID-19來說，被感染但仍未具感染性<icon e></icon> 的時間*平均*為3天，[^latent]加入這個參數對我們的模擬會產生什麼影響呢？

[^latent]: “Assuming an incubation period distribution of mean 5.2 days from a separate study of early COVID-19 cases, we inferred that infectiousness started from 2.3 days (95% CI, 0.8–3.0 days) before symptom onset” (translation: Assuming symptoms start at 5 days, infectiousness starts 2 days before = Infectiousness starts at 3 days) [He, X., Lau, E.H.Y., Wu, P. et al.](https://www.nature.com/articles/s41591-020-0869-5) 「根據另一份對COVID-19病例研究，我們可以假設潛伏期機率分布的平均數為5.2天，並且可以推測在出現症狀的2.3天前（95%信賴區間為0.8-3.0天）病患開始具備可感染性」（翻譯，假設症狀在被感染後第五天出現，病患在出現症狀的兩天前具備可感染性＝可感染性在第三天出現）[He, X., Lau, E.H.Y., Wu, P. et al.](https://www.nature.com/articles/s41591-020-0869-5)

<b style='color:#ff4040'>紅色 <b style='color:#FF9393'>＋粉紅色</b> 曲線</b> 是*現存*病例（具感染性<icon i></icon>＋潛伏<span class="nowrap"><icon e></icon>），</span>    
<b style='color:#888'>灰色曲線</b> 是病例*總數*（現存＋康復<span class="nowrap"><icon r></icon>）：</span>

<div class="sim">
		<iframe src="sim?stage=epi-5" width="800" height="540"></iframe>
</div>

Not much changes! How long you stay <icon e></icon> Exposed changes the ratio of <span class="nowrap"><icon e></icon>-to-<icon i></icon>,</span> and *when* current cases peak... but the *height* of that peak, and total cases in the end, stays the same.

差別不大！潛伏期 <icon e></icon> 的長短會改變 <span class="nowrap"><icon e></icon>與<icon i></icon>的比例</span> 和*現存病例*高峰出現的時間…，但高峰的*高度*和最後的感染總數不會變。

Why's that? Because of the *first*-most important idea in Epidemiology 101:

為什麼會這樣呢？這是因為流行病學導論裡*最重要*的概念：

![](pics/r.png)

It's the *average* number of people an <icon i></icon> infects *before* they recover (or die).


「再生數（Reproduction number）」的縮寫。這是一位<icon i></icon>在*康復前*（或死亡前）傳染的平均人數。 

![](pics/r2.png)

**R** changes over the course of an outbreak, as we get more immunity & interventions.

因著更多人免疫和人為干預，**R**隨著疾病爆發的過程發生變化。

**R<sub>0</sub>** (pronounced R-nought) is what R is *at the start of an outbreak, before immunity or interventions*. R<sub>0</sub> more closely reflects the power of the virus itself, but it still changes from place to place. For example, R<sub>0</sub> is higher in dense cities than sparse rural areas.

**R<sub>0</sub>** （唸作 R-nought）是R在疾病剛爆發時（未有免疫及干預）的值，R<sub>0</sub>比較能反映病毒本身的感染力，但仍因地而異。舉例來說， R<sub>0</sub>在人口稠密的都市比在人煙稀少的地方高。

(Most news articles – and even some research papers! – confuse R and R<sub>0</sub>. Again, science terminology is bad)

（大部分的新聞文章（甚至某些研究論文！）混淆了R和R<sub>0</sub>。再說一次，科學用語很爛。）

The R<sub>0</sub> for "the" seasonal flu is around 1.28[^r0_flu]. This means, at the *start* of a flu outbreak, each <icon i></icon> infects 1.28 others *on average.* (If it sounds weird that this isn't a whole number, remember that the "average" mom has 2.4 children. This doesn't mean there's half-children running about.)


季節性流感的R<sub>0</sub>值大約為1.28[^r0_flu]，這意味著在*剛剛*流感爆發的時候，平均一位<icon i></icon>傳染給1.28個人（如果你覺得這是小數很怪的話，記得「平均」一位母親有2.4個孩子，這不代表有半個孩子跑來跑去。）

[^r0_flu]: “The median R value for seasonal influenza was 1.28 (IQR: 1.19–1.37)” [Biggerstaff, M., Cauchemez, S., Reed, C. et al.](https://bmcinfectdis.biomedcentral.com/articles/10.1186/1471-2334-14-480)「季節流感的R值為1.28（四分位距1.19-1.37）」[Biggerstaff, M., Cauchemez, S., Reed, C. et al.](https://bmcinfectdis.biomedcentral.com/articles/10.1186/1471-2334-14-480)

The R<sub>0</sub> for COVID-19 is estimated to be around 2.2,[^r0_covid] though one *not-yet-finalized* study estimates it was 5.7(!) in Wuhan.[^r0_wuhan]

新冠病毒的R<sub>0</sub>估計為2.2[^r0_covid] ，雖然一份還未定稿的研究估計在武漢的R<sub>0</sub>值為5.5（！）[^r0_wuhan]。

[^r0_covid]: “We estimated the basic reproduction number R0 of 2019-nCoV to be around 2.2 (90% high density interval: 1.4–3.8)” [Riou J, Althaus CL.](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7001239/)

[^r0_wuhan]: “we calculated a median R0 value of 5.7 (95% CI 3.8–8.9)” 「我們計算出的平均R<sub>0</sub>值為5.7（95%信賴區間3.8-3.9）」[Sanche S, Lin YT, Xu C, Romero-Severson E, Hengartner N, Ke R.](https://wwwnc.cdc.gov/eid/article/26/7/20-0282_article)

In our simulations – *at the start & on average* – an <icon i></icon> infects someone every 4 days, over 10 days. "4 days" goes into "10 days" two-and-a-half times. This means – *at the start & on average* – each <icon i></icon> infects 2.5 others. Therefore, R<sub>0</sub> = 2.5. (caveats:[^r0_caveats_sim])

在我們的模擬中（剛開始和平均來說）一位<icon i></icon>十天裡，每四天會感染一個人。「四天」在「十天」裡經過2.5個週期，也就是說 *（剛開始和平均來說）* 傳染給2.5個人，所以R<sub>0</sub> = 2.5 （警告：[^r0_caveats_sim]）

[^r0_caveats_sim]: This is pretending that you're equally infectious all throughout your "infectious period". Again, simplifications for educational purposes. 這是在患者的可感染性在整個「潛伏期」中保持一致，這再一次是為了教育目的所做的簡化。

**Play with this R<sub>0</sub> calculator, to see how R<sub>0</sub> depends on recovery time & new-infection time:**

**玩玩看這個R<sub>0</sub>計算機，看看R<sub>0</sub>和康復時間和感染他人的時間的關係為何。**

<div class="sim">
		<iframe src="sim?stage=epi-6a&format=calc" width="285" height="255"></iframe>
</div>

But remember, the fewer <span class="nowrap"><icon s></icon>s</span> there are, the *slower* <span class="nowrap"><icon s></icon>s</span> become <span class="nowrap"><icon i></icon>s.</span> The *current* reproduction number (R) depends not just on the *basic* reproduction number (R<sub>0</sub>), but *also* on how many people are no longer <icon s></icon> Susceptible. (For example, by recovering & getting natural immunity.)

但記住，<icon s></icon>越少，<icon s></icon>*越慢*成為<icon i></icon>。*當下*的再生數R不只和*基本*再生數R<sub>0</sub>有關，也和不在易感<icon s></icon>的人數有關（例如經由康復和得到天然免疫力。）

<div class="sim">
		<iframe src="sim?stage=epi-6b&format=calc" width="285" height="390"></iframe>
</div>

When enough people have immunity, R < 1, and the virus is contained! This is called **herd immunity**. For flus, herd immunity is achieved *with a vaccine*. Trying to achieve "natural herd immunity" by letting folks get infected is a *terrible* idea. (But not for the reason you may think! We'll explain later.)

當具有免疫力的人夠多的時候，R < 1，疫情被控制住了！這叫做**群體免疫（herd immunity）**。對流感的群體免疫是藉由*疫苗*獲得，藉由很多民眾被感染而取得「天然群體免疫」是很*糟糕*的想法（但可能不是你所想像的原因！我們會在之後解釋。）

Now, let's play the SEIR Model again, but showing R<sub>0</sub>, R over time, and the herd immunity threshold:

讓我們在玩SEIR模型一遍，但這次顯示R<sub>0</sub>、R隨時間的變化和群體免疫閥值：

<div class="sim">
		<iframe src="sim?stage=epi-7" width="800" height="540"></iframe>
</div>

**NOTE: Total cases *does not stop* at herd immunity, but overshoots it!** And it crosses the threshold *exactly* when current cases peak. (This happens no matter how you change the settings – try it for yourself!)

**註：病例總數並不會停在得到群體免疫的時間點，而是在這之後！而且群體免疫*正是在*現存病例的最高峰時產生的（這件事不隨參數改變，你自己試試看！）**

This is because when there are more <span class="nowrap">non-<icon s></icon>s</span> than the herd immunity threshold, you get R < 1. And when R < 1, new cases stop growing: a peak.

這是因為當<span class="nowrap">非<icon s></icon></span>大於群體免疫閥值的時候你會得到 R<1 ，而當 R<1 時候，新病例的增長速度減慢：也就是高峰。

**If there's only one lesson you take away from this guide, here it is** – it's an extremely complex diagram so please take time to fully absorb it:

**如果你只能從這份指南學到一件事的話，就是這件事**——這是一個非常複雜的圖，所以請花時間好好吸收它：

![](pics/r3.png)

**This means: we do NOT need to catch all transmissions, or even nearly all transmissions, to stop COVID-19!**

**這代表：我們不需要找到所有或幾乎所有傳染途徑來阻止COVID-19！**

It's a paradox. COVID-19 is extremely contagious, yet to contain it, we "only" need to stop more than 60% of infections. 60%?! If that was a school grade, that's a D-. But if R<sub>0</sub> = 2.5, cutting that by 61% gives us R = 0.975, which is R < 1, virus is contained! (exact formula:[^exact_formula])

這是個悖論，COVID-19的傳染性超級高，但我們「只需」降低60%的傳染就能遏止它。60%？！如果換算成學校成績的話，那代表D-，但如果R<sub>0</sub>=2.5的話，減少61$的傳染會讓我們得到R=0.975，也就是 R<1。病毒被遏制住了！（正確的公式：[^exact_formula]）

[^exact_formula]: Remember R = R<sub>0</sub> * the ratio of transmissions still allowed. Remember also that ratio of transmissions allowed = 1 - ratio of transmissions *stopped*. 記住 R = R<sub>0</sub> * 傳染成功率。然後記得傳染成功率 = 1 - 傳染*失敗*率。 
    
    Therefore, to get R < 1, you need to get R<sub>0</sub> * TransmissionsAllowed < 1. 
    因此，為了達到 R < 1 ，你需要得到R<sub>0</sub> * 傳染成功率 < 1.
    Therefore, TransmissionsAllowed < 1/R<sub>0</sub>
    因此，傳染成功率 < 1/R<sub>0</sub>
    Therefore, 1 - TransmissionsStopped < 1/R<sub>0</sub>
    因此，1 - 傳染失敗率 < 1/R<sub>0</sub>
    Therefore, TransmissionsStopped > 1 - 1/R<sub>0</sub>
    因此，傳染失敗率 > 1 - 1/R<sub>0</sub>
    Therefore, you need to stop more than **1 - 1/R<sub>0</sub>** of transmissions to get R < 1 and contain the virus!
    因此為了得到 R < 1 和遏制病毒，你需要阻擋多於 ***1-1/R<sub>0</sub>* 的傳染數。

![](pics/r4.png)

(If you think R<sub>0</sub> or the other numbers in our simulations are too low/high, that's good you're challenging our assumptions! There'll be a "Sandbox Mode" at the end of this guide, where you can plug in your *own* numbers, and simulate what happens.)

（如果你覺得 R<sub>0</sub>或模擬裡其它數字太低／太高的話，這很好因為你正在挑戰我們的假設！在這份指南的結尾我們提供一個「沙盒模式」，你可以在那裡試試*你自己*的數字然後看看會發生什麼。）

*Every* COVID-19 intervention you've heard of – handwashing, social/physical distancing, lockdowns, self-isolation, contact tracing & quarantining, face masks, even "herd immunity" – they're *all* doing the same thing:

Getting R < 1.

*所有*你聽過阻擋COVID-19的手段——洗手、社交／肢體距離、封鎖、自主隔離、接觸追蹤和隔離檢疫、戴口罩甚至「群體免疫」——它們都是為了同一件事：

讓 R < 1。

So now, let's use our "epidemic flight simulator" to figure this out: How can we get R < 1 in a way **that also protects our mental health *and* financial health?**

Brace yourselves for an emergency landing...

所以現在讓我們的「流行病飛行模擬器」來解答：如果在確保 **心理健康*和*財政健全的情況下**讓 R < 1？

準備好緊急迫降⋯⋯

<div class="section chapter">
    <div>
		<img src="banners/curve.png" height=480 style="position: absolute;"/>
        <div>接下來的幾個月</div>
    </div>
</div>

...could have been worse. Here's a parallel universe we avoided:

⋯⋯事情可能會變更糟。接下來是我們避免的平行宇宙：

###場景 0：什麼都不做

Around 1 in 20 people infected with COVID-19 need to go to an ICU (Intensive Care Unit).[^icu_covid] In a rich country like the USA, there's 1 ICU bed per 3400 people.[^icu_us] Therefore, the USA can handle 20 out of 3400 people being *simultaneously* infected – or, 0.6% of the population.

每20個感染新冠病毒的人有1個需要進到加護病房[^icu_covid]。以美國為例的富裕國家，每3400個人會分到一張加護病房的病床[^icu_us]。因此美國能處理每3400人有20人得到新冠病毒的狀況——或0.6%的人口。

[^icu_covid]: ["Percentage of COVID-19 cases in the United States from February 12 to March 16, 2020 that required intensive care unit (ICU) admission, by age group" 「在2020年2月12日到3月16間，美國新冠肺炎患者需要進加護病房的百分比，以年齡分段。」]（https://www.statista.com/statistics/1105420/covid-icu-admission-rates-us-by-age-group/）。在*所有*新冠肺炎患者中，4.9%到11.5%的人需要進加護病房。如果我們用最低的百分比來看，這意味著5%或每20位患者中有1人。注意到這個數目和美國的人口結構有關，在老年人更多的國家這個數字會更高，在人口更年輕的國家這個數字會更低。

[^icu_us]: “Number of ICU beds = 96,596”「加護病房病床數＝96,596。」來自[the Society of Critical Care Medicine](https://sccm.org/Blog/March-2020/United-States-Resource-Availability-for-COVID-19) 在2019年美國的人口數為328,200,000。 96,596分之328,200,000約等於1分之3400。 


如果我們將負荷量提高到3倍以上來到2%，以下是我們*完全不做任何事*會發生的情況：

<div class="sim">
		<iframe src="sim?stage=int-1&format=lines" width="800" height="540"></iframe>
</div>

不好。

這是 [3月16號倫敦帝國學院報告](http://www.imperial.ac.uk/mrc-global-infectious-disease-analysis/covid-19/report-9-impact-of-npis-on-covid-19/)的結論：如果我們什麼都不做，加護病房會塞滿病人，而且80%的人口會被感染。
（記得：被感染總數會超越群體免疫）

Even if only 0.5% of infected die – a generous assumption when there's no more ICUs – in a large country like the US, with 300 million people, 0.5% of 80% of 300 million = still 1.2 million dead... *IF we did nothing.*

即使只有0.5%的感染者死亡——在沒有加護病房下很寬鬆的假設——在如美國一樣擁有3億人口的大國，3億中的80%中的0.5%仍代表一百二十萬人死亡⋯⋯*如果我們什麼都不做的話。*

(Lots of news & social media reported "80% will be infected" *without* "IF WE DO NOTHING". Fear was channelled into clicks, not understanding. *Sigh.*)

（許多新聞或社群媒體報導「80%會被感染」卻不講**我們什麼都不做**。恐懼被轉化為點擊數而非理解。*唉*）

###場景 1: 拉平曲線／群體免疫

The "Flatten The Curve" plan was touted by every public health organization, while the United Kingdom's original "herd immunity" plan was universally booed. They were *the same plan.* The UK just communicated theirs poorly.[^yong]

所有的公共衛生機構都在宣傳「拉平曲線」計畫，然而英國原本的「群體免疫」計畫卻受到滿堂倒彩。它們是*一樣的計畫。*只是英國傳達地很糟。

[^yong]: 「他說真正的目標和其它國家一樣：藉由錯開感染的時間來拉長曲線。作為結果，國家可能達到群體免疫；這是伴隨的結果而非目標。[...]政府實際上的新冠病毒行動方案，公開在網路上，完全沒有提到群體免疫。」
    
    來自 [Ed Yong在大西洋雜誌的文章](https://www.theatlantic.com/health/archive/2020/03/coronavirus-pandemic-herd-immunity-uk-boris-johnson/608065/)

然而兩者皆具有致命的缺陷。

First, let's look at the two main ways to "flatten the curve": handwashing & physical distancing.

首先讓我們先來看一樣兩種主要「拉平曲線」的方法：洗手和肢體距離。

Increased handwashing cuts flus & colds in high-income countries by ~25%[^handwashing], while the city-wide lockdown in London cut close contacts by ~70%[^london]. So, let's assume handwashing can reduce R by *up to* 25%, and distancing can reduce R by *up to* 70%:

增加洗手率在高收入國家能減少約25%的流感與感冒[^handwashing]，而倫敦的全城封鎖減少了約70%的近距離接觸[^london]。所以讓我們假設洗手能將R值降到*最多*25%，而社交距離能降低R值*最多*到70% 

[^handwashing]: 「八篇有效的研究報告均指出洗手能降低呼吸道感染的風險，降低幅度為6%到44% [合併值為 24% （95%信賴區間為6-40%）]」為了方便模擬我們取25%。[Rabie, T. and Curtis, V.](https://onlinelibrary.wiley.com/doi/full/10.1111/j.1365-3156.2006.01568.x)。註：如同這篇統合分析指出，關於洗手研究的研究品質（至少在高收入國家）很糟。

[^london]: 「我們發現參與者每日接觸到的人平均減少了73%，這將足夠將R0值從封城前的2.6降低至封城期的0.62 (0.37-0.89)」為了方便模擬我們取70%。[Jarvis and Zandvoort et al](https://cmmid.github.io/topics/covid19/comix-impact-of-physical-distance-measures-on-transmission-in-the-UK.html) 

**Play with this calculator to see how % of <span class="nowrap">non-<icon s></icon>,</span> handwashing, and distancing reduce R:** (this calculator visualizes their *relative* effects, which is why increasing one *looks* like it decreases the effect of the others.[^log_caveat])

**使用這台計算機來觀察<span class="nowrap">非<icon s></icon></span>的百分比、洗手和距離政策如何降低R：** （計算機是將它們之間的*相對*關係視覺化，這就是為什麼提高其中一個*看起來*降低了其它的效應[^log_caveat]）

[^log_caveat]: 如果我們將R用對數尺度畫出來的話，就能避免這層失真⋯⋯但這樣我們就需要解釋什麼是*對數尺度*。

<div class="sim">
		<iframe src="sim?stage=int-2a&format=calc" width="285" height="260"></iframe>
</div>

Now, let's simulate what happens to a COVID-19 epidemic if, starting March 2020, we had increased handwashing but only *mild* physical distancing – so that R is lower, but still above 1:

現在讓我們模擬以下對COVID-19疫情的影響：如果2020年3月增加洗手的比例，搭配些微的社交距離使得R雖然降低了，但仍高於1：

<div class="sim">
		<iframe src="sim?stage=int-2&format=lines" width="800" height="540"></iframe>
</div>

三點註記：

1. 這*降低*了病例總數！**即使沒有達到 R < 1，降低R值仍舊能藉由降低群體免疫以上的病例數來拯救生命。**很多民眾覺得「拉平曲線」只是讓病例發生的時間散開了而沒有降低總數。這在*任何*流行病學101的模型裡都是不可能的。但因為新聞「80%+的人會被感染」報導得好像是不可避免的，民眾以為不管怎樣都沒辦法降低病例總數。*唉。*

2. 由於採取了額外的干預措施，目前的病例在「群體免疫」之前達到「高峰」。實際上，在此模擬中，總病例僅比群體面議高*一點點*-這就是英國的計劃！此時 R < 1，不需要其它的干預措施，而且COVID-19的疫情保持控制！ 好吧，除了一個問題...

3. 加護病房還是會在幾個月後被用光（而且記得，我們*已經*在這些模擬裡把加護病房數增加3倍。）

That was the other finding of the March 16 Imperial College report, which convinced the UK to abandon its original plan. Any attempt at **mitigation** (reduce R, but R > 1) will fail. The only way out is **suppression** (reduce R so that R < 1).

這是帝國學院3月16日報告的另一個發現，說服英國放棄原本的計畫。任何嘗試**緩和**（降低R但R > 1）疫情的嘗試都將失敗，唯一的解決辦法是**抑制**疫情（將R值降到<1）。


![](pics/mitigation_vs_suppression.png)

That is, don't merely "flatten" the curve, *crush* the curve. For example, with a...

也就是說不要緊緊「拉平」曲線。「壓扁」它。舉個例子，用⋯⋯

###場景2：幾個月的封鎖


讓我們看看如果我們用5個月長的封鎖將曲線*壓扁*，將<icon i></icon>降到幾乎為0，然後最後——*終於*——回到正常生活：

<div class="sim">
		<iframe src="sim?stage=int-3&format=lines" width="800" height="540"></iframe>
</div>

喔。

這就是大家說的「第二波疫情」。一旦解除封鎖，我們將再次得到R > 1。所以任何一條<icon i></icon>漏網之魚（或移入的<span class="nowrap"><icon i></icon>）</span>都會造成病例突然增加，這幾乎和場景0——什麼都不做——一樣糟。

**封鎖不是解藥，它只是開始。**

那又怎樣，不然我們一直重複封鎖怎樣？

###場景3：間歇性封鎖

這個解決辦法在帝國學院3月16號的報告第一次被建議，然後再次在哈佛的論文裡被提出來。[^lockdown_harvard]

[^lockdown_harvard]: 「在沒有其它干預手段的情況下，社交距離成功的關鍵指標為是否超過了加護病房數量，為了避免這個情況，社交距離可能需要延長或間歇性實施到2022年。」 [Kissler and Tedijanto et al](https://science.sciencemag.org/content/early/2020/04/14/science.abb5793)

**模擬在這：** （當你嘗試完「預設情況」後，你可以在模擬*運行時*移動滑桿來試試*自己*的封鎖時程！記得你可以暫停和繼續模擬，也可以改變模擬的速率。）

<div class="sim">
		<iframe src="sim?stage=int-4&format=lines" width="800" height="540"></iframe>
</div>

這*會讓*病例數低於加護病房容量！而且這比持續至疫苗上市的18個月封鎖要*好多了*。我們只需要⋯⋯封鎖幾個月，解除封鎖幾個月，持續至疫苗問世（而如果一直沒有疫苗，持續至⋯⋯2020年達到群體免疫）。

注意，畫一條代表「加護病房容量」的線很好，但在這裡我們有很多重要的事情*沒辦法*模擬，例如：

**心理健康：** 孤獨是造成憂鬱、焦慮和自殺的重要因子，而且它造成早死的效應等同每天抽15根菸。[^loneliness]

[^loneliness]: 見 [Holt-Lunstad & Smith 2010的圖6](https://journals.sagepub.com/doi/abs/10.1177/1745691614568352)。 當然，我們要聲明他們發現的是*相關性*，但除非你想嘗試隨機選取人們讓他們過孤獨的人生，我們只能得到觀察性證據。

**財政健全：** 「那經濟怎麼辦」聽起來像是你在乎鈔票多餘人命，但是「經濟」不僅限於股票：它還包含了人們提供食物和居所給他們所愛的人的能力、投資孩子的未來、和享受藝術、美食、電玩——那些使人值得活著的事物。除此之外，貧窮*本身*會帶來對身心健康的可怕影響。

我們並不是在說我們*不該*再次封鎖！我們將會在之後討論「斷路器式」封鎖，但這仍不是理想的辦法

但等一下⋯⋯台灣和韓國不是*已經*在沒有長期封鎖的情況下遏制COVID-19了嗎？

它們怎麼做到的？

###場景4：檢驗、追蹤、隔離

*當然我們\*應該\*在開始的時候跟台灣和韓國做一樣的事情，但現在已經太晚了，我們已經錯過開始的時間。*


但這就是重點！「封鎖不是解方，它只是重新開始⋯⋯」**而一個全新的開始正是我們需要的。**

要了解台灣和南韓遏制疫情的方法，我們需要瞭解一般COVID-19的感染病程[^timeline]:

[^timeline]: **至疾病可傳播平均要3天：**「假設從另一項對COVID-19早期病例的研究，潛伏期的平均值為5.2天，我們以此推斷在病患出現症狀的2.3天前（95%信賴區間 0.8-3.0天）開始具可傳播性。」（翻譯：假設症狀在感染後第5天出現，可傳染性在症狀出現2天前開始＝可傳播性在第3天開始） [He, X., Lau, E.H.Y., Wu, P. et al.](https://www.nature.com/articles/s41591-020-0869-5)  
    
    **平均4天開始能傳染給別人：**「平均[世代]間隔為3.96天（95%信賴區間3.53-4.39天）。」 [Du Z, Xu X, Wu Y, Wang L, Cowling BJ, Ancel Meyers L](https://wwwnc.cdc.gov/eid/article/26/6/20-0357_article)
    
    **發覺症狀平均需要5天：**「潛伏期的中位數估計為5.1天（95%信賴區間4.5-5.8天）」 [Lauer SA, Grantz KH, Bi Q, et al](https://annals.org/AIM/FULLARTICLE/2762808/INCUBATION-PERIOD-CORONAVIRUS-DISEASE-2019-COVID-19-FROM-PUBLICLY-REPORTED)

![](pics/timeline1.png)

如果人們在知道他們自己生病了才自主隔離（也就是說他們發覺症狀），那病毒還是能夠散播：

![](pics/timeline2.png)

而且事實上44%的傳播就是這樣來的：在症狀發生*之前*！ [^pre_symp]

[^pre_symp]: 「我們估計到44%的次代病例（95%信賴區間25-69%）是在初代病例產生症狀前被感染的。」 [He, X., Lau, E.H.Y., Wu, P. et al](https://www.nature.com/articles/s41591-020-0869-5)

但如果我們找到*並隔離*出現症狀的病患最近所接觸的人⋯⋯我們就能藉由超前一步來阻止疾病傳播開來！

![](pics/timeline3.png)

This is called **contact tracing**. It's an old idea, was used at an unprecedented scale to contain Ebola[^ebola], and now it's core part of how Taiwan & South Korea are containing COVID-19!

這叫做**接觸者追蹤**。它是一個老想法，曾以史無前例的規模被用來遏制伊波拉[^ebola]，如今成為台灣和南韓如何遏制COVID-19的核心部分。

[^ebola]: 「接觸者追蹤是賴比瑞亞的關鍵手段，是歷史上流行期間最大的接觸者追蹤工作之一。」 [Swanson KC, Altare C, Wesseh CS, et al.](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6152989/)


（這也讓我們更有效率地實施我們有限的測試，在不需檢驗幾乎所有人的情況下找到潛伏期患者<icon i></icon>。）

Traditionally, contacts are found with in-person interviews, but those *alone* are too slow for COVID-19's ~48 hour window. That's why contact tracers need help, and be supported by – *NOT* replaced by – contact tracing apps. 傳統上接觸者是在訪問病患的過程中被找到的，但*只利用*這些對COVID-19約48小時窗口來說太慢了。這是為什麼接觸追蹤者需要幫忙，並需要接觸追蹤app的幫助——不是被取代。

(這個想法並不是來自「科技宅」：最早是[一個牛津流行病學家的團隊]提出使用app來對抗COVID0-19的方案(https://science.sciencemag.org/content/early/2020/04/09/science.abb6936)。)

等等，追蹤你曾接觸過的人的app⋯⋯？這是不是代表放棄隱私權然後交給老大哥？

當然不是！ **[DP-3T](https://github.com/DP-3T/documents#decentralized-privacy-preserving-proximity-tracing)**，一組流行病學家與密碼學家的團隊（包含我們的其中一員Marcel Salathé）*已經*在開發一款接觸追蹤app——原始碼公開給大眾——，它**不會揭露你的身份、位置、和你接觸的人甚至你*曾接觸的人數* **。

以下是它的原理：

![](pics/dp3t.png)

([這裡可見完整的漫畫](https://ncase.me/contact-tracing/)。關於「惡搞」／偽陽性／等等請見註腳：[^dp3t_details])

[^dp3t_details]: 為了避免「惡搞」（民眾錯誤地聲稱他們被感染），DP-3T協議需要醫院先給你一個一次性的密碼讓你上傳你的資訊。
    
    偽陽性對人工和數位追蹤來說都是問題。但我們仍然可以利用以下兩個辦法來降低偽陽性的出現：1) 只有在Bob聽到例如30+分鐘以上的訊息才通知他們，而不是僅靠一則訊息 2) 如果app*認為*Bob被感染了，那會將Bob交給*人工*追蹤進行進一步的深入追蹤。
    
    其它的議題如資料屏寬、來源完整性和其它的安全性問題，請看[DP-3T的開源白皮書！](https://github.com/DP-3T/documents#decentralized-privacy-preserving-proximity-tracing)

與其他相似的團隊如TCN協議[^tcn]與MIT的PACT[^pact]，他們啟發了蘋果和Google直接將隱私權優先的接觸追蹤植入Android/iOS[^gapple] （不相信Google/蘋果？很好！這個系統美妙的地方是它*不需要*信任！）不久之後，你的地方衛生機構可能會要求你下載一款app，如果它是隱私優先且原始碼公開的軟體，請這麼做！

[^tcn]: [Temporary Contact Numbers：一個去中心化、隱私優先的接觸追蹤協議](https://github.com/TCNCoalition/TCN#tcn-protocol)

[^pact]: [PACT: Private Automated Contact Tracing](https://pact.mit.edu/)

[^gapple]: [蘋果和Google合作開發COVID-19接觸追蹤科技](https://www.apple.com/ca/newsroom/2020/04/apple-and-google-partner-on-covid-19-contact-tracing-technology/)。注意他們*並沒有自己開發*，他們只是創造一個能支援這些軟體的平台。

但那些沒有智慧型手機的民眾怎麼辦？或者感染源是門把怎麼辦？或「真的」無症狀的病例？接觸追蹤app沒辦法抓到所有的傳染源⋯⋯*沒有關係！*我們不需要抓到*所有的*感染源，只需要60%+即能達到 R < 1。

（註腳是關於混淆未產生症狀與「真正的」無症狀感染的抱怨——真正的無症狀感染很罕見：[^rant]）

[^rant]: 很多新聞報導——老實說，很多研究論文——沒有區分「在檢測時還沒有症狀的病例（潛伏期患者）」和「*從未*出現症狀的病患（真正的無症狀感染者）」。唯一能區分他們的方法是持續追蹤。
   
    這就是[這篇研究](https://wwwnc.cdc.gov/eid/article/26/8/20-1274_article)所做的（聲明：「早期出版的文章不被視為最終版。」）在南韓一間爆發COVID-19的電話客服中心，「只有4例（1.9%）在14天的隔離期維持無症狀，他們的家人都沒有被感染。」
    
    所以這代表「真正的無症狀病患」很罕見，而被這些無症狀病患感染更罕見！

隔離*出現症狀*的病例能將R降低最多40%，而隔離他們處於潛伏期／沒有症狀的接觸者能將R降低最多50%[^oxford]:

[^oxford]: 來自同一篇推薦使用app對抗COVID-19的牛津研究：[Luca Ferretti & Chris Wymant et al](https://science.sciencemag.org/content/early/2020/04/09/science.abb6936/tab-figures-data) 見圖2。在假設 R<sub>0</sub> = 2.0的情況下，他們發現： 
    
    * 有症狀患者貢獻0.8給R (40%)
    * 潛伏期患者貢獻0.9給R (45%)
    * 無症狀患者貢獻0.1給R (5%，不過他們的模型有不確定性所以這可能低很多)
    * 環境感染源如門把貢獻0.2給R (10%)

    將潛伏期和無症狀患者加起來(45% + 5%)就會得到50%的R！

<div class="sim">
		<iframe src="sim?stage=int-4a&format=calc" width="285" height="340"></iframe>
</div>

因此，即使沒有將100%的接觸者隔離起來，我們還是能在*沒有封鎖*的情況下得到 R < 1！對心理健康和財務健康要好多了。（對那些需要自主隔離／隔離檢疫的民眾，*政府應該要補助他們的花費*——包含檢測費用、工作保障、提供有薪假等等。仍然比間歇性封鎖要好多了。）

然後我們維持R < 1直到疫苗問世，將可感染的<icon s></icon>變成免疫的<icon r></icon>。用*正確的*方法達到群體免疫： 

<div class="sim">
		<iframe src="sim?stage=int-4b&format=calc" width="285" height="230"></iframe>
</div>

（註：這個計算器假設疫苗百分之百有效。只要記得在現實中，我們需要施打*大於*「群體免疫」數量的疫苗來*真正*的群體免疫。）

好了，廢話夠了。以下是這些情況的模擬：

1. 數個月的封鎖，直到我們可以⋯⋯
2. 轉變成「檢測、追蹤、隔離」直到我們可以⋯⋯
3. 給夠多人施打疫苗，這意味著⋯⋯
4. 我們贏了。

<div class="sim">
		<iframe src="sim?stage=int-5&format=lines" width="800" height="540"></iframe>
</div>

就是這樣！這就是我們如果將飛機緊急迫降。

這就是我們如何打敗COVID-19。

⋯⋯

但如果事情*仍然*往不好的方向發展呢？事情已經很糟了。這是恐懼。這很好！恐懼給我們力量制定*備案*。

悲觀者發明降落傘。

###場景4+：全民戴口罩、夏天、斷路器

如果R<sub>0</sub>比我們想的要高得多，而且以上所有的手段，甚至是輕微的距離（？？），*仍沒有*辦法讓 R < 1呢？

記住，即使我們沒辦法讓 R < 1，降低R值仍然能夠減少病例總數，因此挽救生命。即使是這樣，R < 1仍然是理想的情況，所以這裡提供其他降低R的方法。

**全民戴口罩：**

*「等等」*你可能想*「我以為口罩沒辦法病免你生病？」*

You're right. Masks don't stop you from getting sick[^incoming]... they stop you from getting *others* sick.

你是對的。口罩沒辦法避免你生病[^incoming]⋯⋯他們避免你將病傳染給*別人*。

[^incoming]: 「沒有任何一種手術面罩表現出足夠的過濾表現和貼合臉部的特徵，使他們能被視為呼吸道保護器材。」 [Tara Oberg & Lisa M. Brosseau](https://www.sciencedirect.com/science/article/pii/S0196655307007742)

[^outgoing]: 「我們觀察到的氣膠降低3.4倍 [減少70%]，加上Johnson等人的研究發現大型飛沫幾乎完全消除，顯示患者帶著醫用口罩可能對疾病傳播產生顯著的臨床影響。」[Milton DK, Fabian MP, Cowling BJ, Grantham ML, McDevitt JJ](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3591312/)

[^homemade]: [Davies, A., Thompson, K., Giri, K., Kafatos, G., Walker, J., & Bennett, A](https://www.cambridge.org/core/journals/disaster-medicine-and-public-health-preparedness/article/testing-the-efficacy-of-homemade-masks-would-they-protect-in-an-influenza-pandemic/0921A05A69A9419C862FA2F35F819D55) 見表1：對於兩項細菌氣膠的測試，百分之百純棉的T恤約有醫用口罩2/3的過濾力。

![](pics/masks.png)

我們把這些效應量化：*患者戴口罩*減低感冒和流感病毒氣膠的70%。[^outgoing]傳染率減低70%代表和封城的效應一樣大！

然而我們並不知道口罩*針對*COVID-19的效應有多大，科學上我們只應該發表有95%信心的發現。（⋯⋯應該。[^replication]）在2020年5月1日我們對於口罩的效應只有「低於95%的信心」。

[^replication]: 一位真正的科學家讀到這句話可能正在哈哈大笑。見：[p-hacking](https://en.wikipedia.org/wiki/Data_dredging), [再現性危機](https://en.wikipedia.org/wiki/Replication_crisis))

但對付疫情就像玩牌，**Make bets only when you're 95% sure, and you'll lose everything at stake.** 正如一篇近期在英國醫學期刊(BMJ)關於口罩的論文提到的[^precautionary]，我們*必須*在不確定中做利弊分析。像這樣：

[^precautionary]: 「現在是使用預防原則的時候了。」 [Trisha Greenhalgh et al \[PDF\]](https://www.bmj.com/content/bmj/369/bmj.m1435.full.pdf)

成本：如果自製衣物口罩（效用大約是醫用口罩的2/3[^homemade]），超級便宜。醫用口罩比較貴但還是很便宜。

好處：即使只有5成的機會醫用口罩能降低70%的傳播，5成的機會它們完全沒用，*期望值*仍舊是35%，這跟半封城一樣！因為不確定性，我們猜測醫用口罩能降低R值最多至35%（再一次說你可以藉由改變參數來挑戰我們的假設）。

<div class="sim">
		<iframe src="sim?stage=int-6a&format=calc" width="285" height="380"></iframe>
</div>

（其它支持／反對口罩的論點：[^mask_args]）

[^mask_args]: **「我們需要為醫院省下物資。」** *完全同意。*但這比較是支持增加口罩產量的論述，而不是分配。因為同一時間我們可以用衣物做口罩。

   **「口罩很難戴得正確。」**照世衛指南洗手也很困難——認真的，「第三步：右手掌在左手背上」？！——但我們仍然建議洗手，因為不完美仍比什麼都不做好。
   
   **「這會讓人們更輕忽洗手和社交距離。」** 的確，安全帶讓人們忽略交通號誌，牙線讓人們亂吃。但認真說，我們會往相反的方向論證：口罩是一個*實體化*的提醒——而且在東亞，口罩是團結的象徵！    

*單單使用*口罩沒辦法達到 R < 1。但如果洗手加「檢驗、追蹤、隔離」將R降低至1.10，只需1/3的人戴口罩就能將R降到1以下，成功遏制病毒！

**夏天：**

Okay，這不是我們能掌握的「手段」，但這會有幫助！一些新聞報導指出夏天不會對疫情造成任何影響，他們對一半：夏天不會讓 R < 1，但*會*降低R。

對COVID-19來說，每增加攝氏1度（華氏1.8度）會讓R值降低1.2%。[^heat]紐約市夏冬溫差是26%，所以夏天會讓R降低約31%。

[^heat]: 「溫度每增加攝氏1度[...]R降低0.0225。」和「這一百座城市的平均R值為1.83。」 0.0225 ÷ 1.83 = ~1.2%。 [Wang, Jingyuan and Tang, Ke and Feng, Kai and Lv, Weifeng](https://papers.ssrn.com/sol3/Papers.cfm?abstract_id=3551767)

[^nyc_heat]: 2019年在中央公園，最熱的月份（七月）是79.6°F，最冷的月份（一月）是32.5°F，溫差是47.1°F或約26°C。 [PDF from Weather.gov](https://www.weather.gov/media/okx/Climate/CentralPark/monthlyannualtemp.pdf)

<div class="sim">
		<iframe src="sim?stage=int-6b&format=calc" width="285" height="220"></iframe>
</div>

夏天本身不會讓 R < 1，但如果我們只有有限的資源，我們可以在夏天花少一點——這樣我們為冬天做預備。

**「斷路器式」封鎖：**

如果這一切都沒辦法讓 R < 1⋯⋯我們還是能再封鎖一次。

但我們不需要在持續兩個月封鎖／一個月解封的循環！因為R已經被降低了，我們只需要在疫苗問世前實施一兩次「斷路器式」的封鎖即可（最近新加坡就不得不這麼做，「雖然」他們已經控制疫情四個月了。這不代表失敗：這是成功的*代價*。）

以下是一個「懶惰例子」的模擬：

1. 封鎖，然後
2. 適度的衛生＋「檢測、追蹤、隔離」＋適度的全民口罩政策，然後
3. 在疫苗問世前再一次「斷路器式」的封鎖。

<div class="sim">
		<iframe src="sim?stage=int-7&format=lines&height=620" width="800" height="620"></iframe>
</div>

不要說我們還有*一堆*手段可以再進一步壓制R：

* 旅遊限制／隔離檢疫
* 在商場和學校量測體溫
* 公共場所全面消毒
* [將握手改為碰腳](https://twitter.com/V_actually/status/1233785527788285953)
* 和其它一切人類的創造力將帶來
. . .

我們希望這些計畫能帶給你希望。

**即使在悲觀的情況，在保全心理健康和經濟的前提下打敗COVID-19仍是可能的。** 將封鎖視為「重啟鍵」，用隔離病患來保持 R < 1＋保護隱私的接觸追蹤＋口罩（至少自製口罩）⋯⋯生活可以幾乎回歸正常！

當然，你可能會有雙乾澀的手，但你可以到漫畫店約會！你可以和朋友出門去看最新的好萊塢大戲。你可以去圖書館觀察人群，享受人們*活著*從事日常事務的喜悅。

即使在最壞的情況下⋯⋯生命仍能堅持下去。

所以讓我們為*最壞*的幾個情況做計畫。我們會在水面降落，準備好你的救生衣，跟隨指示燈到緊急逃生口：

<div class="section chapter">
    <div>
		<img src="banners/curve.png" height=480 style="position: absolute;"/>
        <div>接下來的幾年</div>
    </div>
</div>

你得到新冠肺炎並且復原了，或者你接種了疫苗。不管哪種情況，你現在都有免疫力⋯⋯

⋯⋯*能持續多久？*

* COVID-19最親近的近親為SARS，SARS的倖存者有2年的免疫力。[^SARS immunity]
* 造成普通感冒的冠狀病毒會給你8個月的免疫力。[^cold immunity]
* 有些患者從COVID-19康復然後再被檢測出陽性，但目前我們仍不清楚這是不是偽陽性。[^unclear]
* One *not-yet-peer-reviewed* study on monkeys showed immunity to the COVID-19 coronavirus for at least 28 days.一篇還未經同行審查關於猴子的研究顯示對新冠病毒的免疫力至少能持續28天。[^monkeys]

但人體對COVID-19的免疫力*有多長*，在2020年5月1日的現在仍舊是大哉問。

[^SARS immunity]: “SARS-specific antibodies were maintained for an average of 2 years [...] Thus, SARS patients might be susceptible to reinfection ≥3 years after initial exposure.” [Wu LP, Wang NC, Chang YH, et al.](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2851497/) "Sadly" we'll never know how long SARS immunity would have really lasted, since we eradicated it so quickly.

[^cold immunity]: “We found no significant difference between the probability of testing positive at least once and the probability of a recurrence for the beta-coronaviruses HKU1 and OC43 at 34 weeks after enrollment/first infection.” [Marta Galanti & Jeffrey Shaman (PDF)](http://www.columbia.edu/~jls106/galanti_shaman_ms_supp.pdf)

[^unclear]: “Once a person fights off a virus, viral particles tend to linger for some time. These cannot cause infections, but they can trigger a positive test.” [from STAT News by Andrew Joseph](https://www.statnews.com/2020/04/20/everything-we-know-about-coronavirus-immunity-and-antibodies-and-plenty-we-still-dont/)

[^monkeys]: From [Bao et al.](https://www.biorxiv.org/content/10.1101/2020.03.13.990226v1.abstract) *Disclaimer: This article is a preprint and has not been certified by peer review (yet).* Also, to emphasize: they only tested re-infection 28 days later. 

For these simulations, let's say it's 1 year.
**Here's a simulation starting with 100% <span class="nowrap"><icon r></icon>**,</span> exponentially decaying into susceptible, no-immunity <span class="nowrap"><icon s></icon>s</span> after 1 year, on *average*, with variation:

<div class="sim">
		<iframe src="sim?stage=yrs-1&format=lines&height=600" width="800" height="600"></iframe>
</div>

Return of the exponential decay!

This is the **SEIRS Model**. The final "S" stands for <icon s></icon> Susceptible, again.

![](pics/seirs.png)

Now, let's simulate a COVID-19 outbreak, over 10 years, with no interventions... *if immunity only lasts a year:*

<div class="sim">
		<iframe src="sim?stage=yrs-2&format=lines&height=600" width="800" height="600"></iframe>
</div>

In previous simulations, we only had *one* ICU-overwhelming spike. Now, we have several, *and* <icon i></icon> cases come to a rest *permanently at* ICU capacity. (Which, remember, we *tripled* for these simulations)

R = 1, it's **endemic.**

Thankfully, because summer reduces R, it'll make the situation better:

<div class="sim">
		<iframe src="sim?stage=yrs-3&format=lines&height=640" width="800" height="640"></iframe>
</div>

Oh.

Counterintuitively, summer makes the spikes worse *and* regular! This is because summer reduces new <span class="nowrap"><icon i></icon>s,</span> but that in turn reduces new immune <span class="nowrap"><icon r></icon>s.</span> Which means immunity plummets in the summer, *creating* large regular spikes in the winter.

Thankfully, the solution to this is pretty straightforward – just vaccinate people every fall/winter, like we do with flu shots:

**(After playing the recording, try simulating your own vaccination campaigns! Remember you can pause/continue the sim at any time)**

<div class="sim">
		<iframe src="sim?stage=yrs-4&format=lines" width="800" height="540"></iframe>
</div>

But here's the scarier question:

What if there's no vaccine for *years*? Or *ever?*

**To be clear: this is unlikely.** Most epidemiologists expect a vaccine in 1 to 2 years. Sure, there's never been a vaccine for any of the other coronaviruses before, but that's because SARS was eradicated quickly, and "the" common cold wasn't worth the investment. 

Still, infectious disease researchers have expressed worries: What if we can't make enough?[^vax_enough] What if we rush it, and it's not safe?[^vax_safe]

[^vax_enough]: “If a coronavirus vaccine arrives, can the world make enough?” [by Roxanne Khamsi, on Nature](https://www.nature.com/articles/d41586-020-01063-8)

[^vax_safe]: “Don’t rush to deploy COVID-19 vaccines and drugs without sufficient safety guarantees” [by Shibo Jiang, on Nature](https://www.nature.com/articles/d41586-020-00751-9)

Even in the nightmare "no-vaccine" scenario, we still have 3 ways out. From most to least terrible:

1) Do intermittent or loose R < 1 interventions, to reach "natural herd immunity". (Warning: this will result in many deaths & damaged lungs. *And* won't work if immunity doesn't last.)

2) Do the R < 1 interventions forever. Contact tracing & wearing masks just becomes a new norm in the post-COVID-19 world, like how STI tests & wearing condoms became a new norm in the post-HIV world.

3) Do the R < 1 interventions until we develop treatments that make COVID-19 way, way less likely to need critical care. (Which we should be doing *anyway!*) Reducing ICU use by 10x is the same as increasing our ICU capacity by 10x:

**Here's a simulation of *no* lasting immunity, *no* vaccine, and not even any interventions – just slowly increasing capacity to survive the long-term spikes:**

<div class="sim">
		<iframe src="sim?stage=yrs-5&format=lines" width="800" height="540"></iframe>
</div>

Even under the *worst* worst-case scenario... life perseveres.

. . .

Maybe you'd like to challenge our assumptions, and try different R<sub>0</sub>'s or numbers. Or try simulating your *own* combination of intervention plans!

**Here's an (optional) Sandbox Mode, with *everything* available. (scroll to see all controls) Simulate & play around to your heart's content:**

<div class="sim">
		<iframe src="sim?stage=SB&format=sb" width="800" height="540"></iframe>
</div>

This basic "epidemic flight simulator" has taught us so much. It's let us answer questions about the past few months, next few months, and next few years.

So finally, let's return to...

<div class="section chapter">
    <div>
		<img src="banners/curve.png" height=480 style="position: absolute;"/>
        <div>The Now</div>
    </div>
</div>

Plane's sunk. We've scrambled onto the life rafts. It's time to find dry land.[^dry_land]

[^dry_land]: Dry land metaphor [from Marc Lipsitch & Yonatan Grad, on STAT News](https://www.statnews.com/2020/04/01/navigating-covid-19-pandemic/)

Teams of epidemiologists and policymakers ([left](https://www.americanprogress.org/issues/healthcare/news/2020/04/03/482613/national-state-plan-end-coronavirus-crisis/), [right](https://www.aei.org/research-products/report/national-coronavirus-response-a-road-map-to-reopening/ ), and [multi-partisan](https://ethics.harvard.edu/covid-roadmap)) have come to a consensus on how to beat COVID-19, while protecting our lives *and* liberties.

Here's the rough idea, with some (less-consensus) backup plans:

![](pics/plan.png)

So what does this mean for YOU, right now?

**For everyone:** Respect the lockdown so we can get out of Phase I asap. Keep washing those hands. Make your own masks. Download a *privacy-protecting* contact tracing app when those are available next month. Stay healthy, physically & mentally! And write your local policymaker to get off their butt and...

**For policymakers:** Make laws to support folks who have to self-isolate/quarantine. Hire more manual contact tracers, *supported* by privacy-protecting contact tracing apps. Direct more funds into the stuff we should be building, like...

**For builders:** Build tests. Build ventilators. Build personal protective equipment for hospitals. Build tests. Build masks. Build apps. Build antivirals, prophylactics, and other treatments that aren't vaccines. Build vaccines. Build tests. Build tests. Build tests. Build hope. 

Don't downplay fear to build up hope. Our fear should *team up* with our hope, like the inventors of airplanes & parachutes. Preparing for horrible futures is how we *create* a hopeful future.

The only thing to fear is the idea that the only thing to fear is fear itself.
