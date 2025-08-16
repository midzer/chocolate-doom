# Emscripten

## Build

```
mkdir build
cd build
emcmake cmake ..
emmake make
```

## Link

```
emcc -flto -O3 -fno-rtti -fno-exceptions *.o ../../doom/libdoom.a ../../../opl/libopl.a ../../../textscreen/libtextscreen.a ../../../pcsound/libpcsound.a -o index.html -sUSE_SDL=2 -sUSE_SDL_MIXER=2 -sSDL2_MIXER_FORMATS='["mid"]' -sUSE_LIBPNG -sASYNCIFY -sASYNCIFY_ONLY=["main","I_OPL_InitMusic","OPL_Detect","D_DoomLoop","TryRunTics","I_FinishUpdate","SDL_Delay","SDL_RenderPresent","GLES2_RenderPresent","Emscripten_GLES_SwapWindow","dynCall_v"] -sASYNCIFY_IGNORE_INDIRECT -sENVIRONMENT=web --preload-file doom1.wad -Wl,-u,htons,-u,ntohs --closure 1 -sINITIAL_HEAP=32mb
```
