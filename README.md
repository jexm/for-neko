for-neko
========
<div id="body">
				<h2 id="neko">neko</h2>

<p>The <code>neko</code> command will run a file which contains compiled Neko bytecode. If the file has a <code>.n</code>, you can omit it.</p>

<p><code>neko &lt;bytecode_file&gt;</code></p>

<h3 id="interpretive_mode">Interpretive mode</h3>

<p>To disable the JIT and only run interpreted code, use</p>

<p><code>neko -interp &lt;bytecode_file&gt;</code></p>

<h3 id="statistics">Statistics</h3>

<p>Some limited statistics are available using</p>

<p><code>neko -stats &lt;bytecode_file&gt;</code></p>

<p>This will print out how much time is spent in some functions and how many times they are called. It is mostly limited to C function calls.</p>

<h2 id="nekoc">nekoc</h2>

<h3 id="compiling">Compiling</h3>

<p>The primary purpose of <code>nekoc</code> is to compile Neko code to Neko bytecode. It will output a file with the file’s extension replaced with <code>.n</code>.</p>

<p><code>nekoc &lt;source_file&gt;</code></p>

<h3 id="linking">Linking</h3>

<p>Several bytecode files can be joined together into a single file.</p>

<p><code>nekoc -link &lt;output_file_name&gt; &lt;bytecode_file&gt; &lt;bytecode_file&gt; ...</code></p>

<p>This is very useful if you are planning on building a stand alone executable using <code>nekotools</code>.</p>

<h3 id="console">Console</h3>

<p>There is a read-execute-print loop available using <code>nekoc</code>. To use this, type in the code and then <code>!</code> to execute it. The results will be shown.</p>

<p><code>nekoc -console</code></p>

<p><em>Note: local variables (declared with <code>var</code>) will not be kept in scope after the <code>!</code> is used to execute the code.</em></p>

<h3 id="dumping_bytecode">Dumping bytecode</h3>

<p>It can also dump the bytecode from a compiled file. It will output a file with <code>.dump</code> as the extension.</p>

<p><code>nekoc -d &lt;bytecode_file&gt;</code></p>

<h3 id="stripping_bytecode">Stripping bytecode</h3>

<p>Debugging information and global names can be stripped from compiled bytecode. This is done in place, it does not create a new file.</p>

<p><code>nekoc -z &lt;bytecode_file&gt;</code></p>

<h3 id="prettifying_code">Prettifying code</h3>

<p><code>nekoc</code> can also create a properly formatted version of a source file. This command will create a new file. For example, if the source file is named “test.neko”, the new file will be called “test2.neko”.</p>

<p><code>nekoc -p &lt;source_file&gt;</code></p>

<h3 id="documentation">Documentation</h3>

<p>Documentation can be produced from comments in Neko source code. This will produce an HTML file.</p>

<p><code>nekoc -doc &lt;source_file&gt;</code></p>

<h3 id="options">Options</h3>

<p>Verbosity can be turned on with <code>-v</code>.</p>

<p>The output directory can be set with <code>-o &lt;directory&gt;</code>.</p>

<h2 id="nekotools">nekotools</h2>

<h3 id="webserver">Webserver</h3>

<p>You can run a webserver that serves up pages using Neko code.</p>

<p><code>nekotools server</code></p>

<p>Options:</p>

<ul>
<li><code>-h &lt;domain&gt;</code> - set hostname</li>

<li><code>-p &lt;port&gt;</code> - set port</li>

<li><code>-d &lt;directory&gt;</code> - set base directory</li>

<li><code>-log &lt;file&gt;</code> - set log file</li>

<li><code>-rewrite</code> - activate pseudo mod-rewrite for smart urls</li>
</ul>

<p>URLs will be matched to <code>.n</code> files in the server directory. For example, http://localhost:2000/test/ will execute and display the results from <code>test.n</code> file, if it exists.</p>

<h3 id="standalone_executable">Standalone executable</h3>

<p>It is possible to create standalone executables from Neko bytecode. Note, however, that you will probably still need <code>libneko.so</code> or <code>libneko.dll</code> unless they are statically linked to <code>neko</code>.</p>

<p>This will output an executable file with no extension.</p>

<p><code>nekotools boot &lt;bytecode_file&gt;</code></p>

<h2 id="nekoml">nekoml</h2>

<p>This program compiles NekoML files.</p>

<p><code>nekoml &lt;source_file&gt;</code></p>
			</div>
