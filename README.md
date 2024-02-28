# نصب پایتون

پایتون بروی سیستم عامل های مک و لینوکس ( اکثر توزیع ها) به صورت پیش فرض نصب می باشد. برای نصب آخرین نسخه پایتون می توانید به آموزش مربوطه در این صفحه مراجعه کنید.

## نصب در ویندوز

<ol dir="rtl">
	<li>
		<p>از آدرس <a href="https://www.python.org/downloads">https://www.python.org/downloads</a> آخرین نسخه پایتون دانلود می کنیم.</p>
	</li>
	<li>
		<p>
		بعد از اجرا فایل دانلود شده، در پنجره نصب، قسمت پایین، تیک گزینه Add python.exe to PATH فعال می کنیم. با فعال بودن این گزینه امکان اجرا دستورات پایتون در محیط ترمینال میسر می شود.
		</p>
	</li>
	<li>
		<p>برای اطمینان از صحت فرایند نصب، ابتدا پنجره ترمینال ( PowerShell یا Command Prompt ) باز می کنیم :</p>
		<ul dir="rtl">
			<li>
				<p>روش اول : در جستجوی ویندوز عبارت Terminal جستجو می کنیم</p>
			</li>
			<li>
				<p>روش دوم : با کلیدهای ترکیبی <kbd>Windows Key</kbd> + <kbd>R</kbd> پنجره Run باز می شود سپس عبارت cmd تایپ، سپس اجرا می کنیم</p>
			</li>
		</ul>
	</li>
	<li>
		<p >با اجرای دستور ذیل در محیط ترمینال نسخه پایتون نصب شده نمایش داده می شود.</p>
        <div dir="ltr" align="left">
            <pre><code>python --version</code></pre>
        </div>
	</li>
	<li>
		<p>با اجرای دستور ذیل در محیط ترمینال نسخه pip نصب شده نمایش داده می شود. ابزار pip به همراه پایتون نصب می شود و وظیفه مدیریت کتابخانه ها دارد.</p>
        <div dir="ltr" align="left">
            <pre><code>pip --version</code></pre>
        </div>
	</li>
</ol>




در صورتیکه مراحل 4 و 5 در پنجره ترمینال، نسخه نرم افزار نمایش داده نشد، فرایند نصب تکرار کنید.

## نصب در اوبونتو / دبیان

<ol dir="rtl">
<li>
	<p>
	در محیط Application به دنبال عبارت Terminal می گردیم.
	</p>
	<ul dir="rtl">
		<li>
			<p>
				روش اول : با کلیدهای ترکیبی <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>T</kbd> پنجره ترمینال باز می شود.
			</p>
		</li>
		<li>
			<p>
			روش دوم : در محیط Application به دنبال عبارت Terminal می گردیم.
			</p>
		</li>
	</ul>
</li>
<li>
	<p>
		با دستور ذیل لیست آخرین پکیج های موجود در مخزن دریافت می کنیم.
	</p>
	<blockquote>
	دستور sudo برای اجرای دستورات با سطح دسترسی مدیر سیستم می باشد. ( مثل Run as administrator در ویندوز )
	</blockquote>
	<div dir="ltr" align="left">
		<pre><code>sudo apt-get update</code></pre>
	</div>
</li>
<li>
	<p>
		این دستور پکیج های نصب شده از قبل، به آخرین نسخه موجود بروزرسانی می کند.
	</p>
	<div dir="ltr" align="left">
		<pre><code>sudo apt-get upgrade</code></pre>
	</div>
</li>
<li>
	<p>
		برای نصب آخرین نسخه پایتون باید از source code پایتون، build بگیریم. این فرایند نیاز به نصب پکیج های ذیل دارد.
	</p>
	<div dir="ltr" align="left">
		<pre><code>sudo apt-get install -y make build-essential libssl-dev zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev libncursesw5-dev xz-utils tk-dev liblzma-dev tk-dev</code></pre>
	</div>
</li>
<li>
	<p>
		دایرکتوری ترمینال، به محلی که قصد دانلود source code داریم جا به جا می کنیم.
	</p>
	<blockquote>
		دایرکتوری tmp محل نگهداری فایل های موقتی می باشد، به عبارت دیگر محتوای این دایرکتوری بعد از هر بار reset حذف می شود.
	</blockquote>
	<div dir="ltr" align="left">
		<pre><code>cd /tmp/</code></pre>
	</div>
</li>
<li>
	<p>
		ابزار wget وظیفه دانلود فایل را دارد. به کمک این ابزار فایل فشرده source code پایتون دانلود می کنیم. ( آدرس دانلود نسخه های مختلف source code در سایت پایتون موجود می باشد )
	</p>
	<div dir="ltr" align="left">
		<pre><code>wget https://www.python.org/ftp/python/3.11.1/Python-3.11.1.tgz</code></pre>
	</div>
</li>
<li>
	<p>
		به محتوای این فایل فشرده باید دسترسی داشته باشیم برای اینکار با ابزار tar محتوای این فایل خارج می کنیم.
	</p>
	<div dir="ltr" align="left">
		<pre><code>tar xzf Python-3.11.1.tgz</code></pre>
	</div>
	<blockquote>
		<p>
			به هریک از حروف xzf که وظیفه اعمال تنظیماتی روی ابزار دارند flag گفته میشه. هرکدام از این کاراکترها اطلاعات مشخصی به ابزار tar می دهد :
		</p>
		<ul dir="rtl">
			<li>
				<strong>x :</strong> عمل استخراج ( Extract ) انجام بشه.
			</li>
			<li>
				<strong>z :</strong> این فایل با الگوریتم gzip فشرده شده. ( از پسوند tgz می فهمیم ).
			</li>
			<li>
				<strong>f :</strong> هدف یک فایل می باشد.
			</li>
		</ul>
	</blockquote>
</li>
<li>
	<p>
		محتوا درون دایرکتوری جدیدی **به نام همان فایل** ریخته شده. دایرکتوری از مکان فعلی به درون دایرکتوری جدید ساخته شده منتقل می کنیم.
	</p>
	<blockquote>
		<p>
			دقت شود که محیط ترمینال به سایز حروف حساس می باشد. در اینجا دایرکتوری با P بزرگ شروع شده.
on-3.11.1 با python-3.11.1 فرق داره !!! خیلی دقت بشه.
		</p>
	</blockquote>
	<div dir="ltr" align="left">
		<pre><code>cd Python-3.11.1</code></pre>
	</div>
</li>
<li>
	<p>
		نوبت به build گرفتن source code و نصب پایتون می باشد.
	</p>
	<div dir="ltr" align="left">
		<pre><code>sudo ./configure --enable-optimizations</code></pre>
	</div>
	<div dir="ltr" align="left">
		<pre><code>sudo make altinstall</code></pre>
	</div>
</li>
<li>
	<p>
		برای اطمینان از صحت فرایند نصب، دستور ذیل وارد می کنیم.
	</p>
	<div dir="ltr" align="left">
		<pre><code>python3.11</code></pre>
	</div>
</li>
</ol>

![ubuntu-check-version](img/ubuntu-check-version.PNG)

