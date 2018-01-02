## Building on Windows

Install Visual C++ Build Tools 2015 (v14.0)
	- in the setup wizard, mark `Windows 10 SDK`, it has some files necessary for the build
	http://landinghub.visualstudio.com/visual-cpp-build-tools
Install GNU Make for windows, and put its `/bin` folder in your `PATH`
	- Download `Complete package, except sources`
	http://gnuwin32.sourceforge.net/packages/make.htm

Open Visual C++ 2015 x64 Native Build Tools Command Prompt 

Navigate to the pyimgui folder
```
make build
```
(or `> pipenv run make build` if you're using pipenv)

## Issues
`pyimgui/ci/completion.py` seems to fail:
```
python ci/completion.py -o README.md with-pxd imgui/cimgui.pxd
Traceback (most recent call last):
  File "ci/completion.py", line 108, in <module>
    cli(obj={})
  File "C:\Users\lubieowoce\.virtualenvs\pyimgui-vcXT3jSF\lib\site-packages\click\core.py", line 722, in __call__
    return self.main(*args, **kwargs)
  File "C:\Users\lubieowoce\.virtualenvs\pyimgui-vcXT3jSF\lib\site-packages\click\core.py", line 697, in main
    rv = self.invoke(ctx)
  File "C:\Users\lubieowoce\.virtualenvs\pyimgui-vcXT3jSF\lib\site-packages\click\core.py", line 1066, in invoke
    return _process_result(sub_ctx.command.invoke(sub_ctx))
  File "C:\Users\lubieowoce\.virtualenvs\pyimgui-vcXT3jSF\lib\site-packages\click\core.py", line 895, in invoke
    return ctx.invoke(self.callback, **ctx.params)
  File "C:\Users\lubieowoce\.virtualenvs\pyimgui-vcXT3jSF\lib\site-packages\click\core.py", line 535, in invoke
    return callback(*args, **kwargs)
  File "C:\Users\lubieowoce\.virtualenvs\pyimgui-vcXT3jSF\lib\site-packages\click\decorators.py", line 17, in new_func
    return f(get_current_context(), *args, **kwargs)
  File "ci/completion.py", line 53, in with_pxd
    output(done_count, all_count, ctx.obj['badge_output'])
  File "ci/completion.py", line 84, in output
    float(done_count)/all_count * 100,
ZeroDivisionError: float division by zero
make: *** [build] Error 1
```

