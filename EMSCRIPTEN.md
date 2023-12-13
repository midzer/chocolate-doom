# Emscripten

## Build

```
mkdir build && cd build
emcmake cmake ..
```

## Link

emcc -fno-rtti -fno-exceptions --Wl,-u,htons,-u,ntohs -flto -O3 *.o ../../doom/libdoom.a ../../../opl/libopl.a ../../../textscreen/libtextscreen.a ../../../pcsound/libpcsound.a -o index.html -sUSE_SDL=2 -sUSE_SDL_MIXER=2 -sSDL2_MIXER_FORMATS='["mid"]' -sUSE_LIBPNG -sASYNCIFY -sASYNCIFY_ONLY=["main","D_DoomLoop","TryRunTics","I_FinishUpdate","SDL_Delay","GLES2_RenderPresent","Emscripten_GLES_SwapWindow","dynCall_v"] -sASYNCIFY_IGNORE_INDIRECT -sINITIAL_MEMORY=64MB -sENVIRONMENT=web --preload-file="dgguspat@/etc/timidity" --preload-file doom1.wad --preload-file default.cfg --preload-file chocolate-doom.cfg --closure 1
